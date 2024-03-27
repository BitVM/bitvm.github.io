# SNARK Verifier in Bitcoin Script

A plan to implement a universal SNARK verifier in Bitcoin Script to run it in [BitVM2](/bitvm2.md).

## Possible Proof Systems
- Groth16
- [FFlonk](https://eprint.iacr.org/2021/1167)
- FFlonk + slonk

All three can operate over the bn254 curve.

Example implementations
- [snarkjs](https://github.com/iden3/snarkjs)


## Code Modules 
- Lamport signatures / Winternitz signatures
- u256 arithmetic
  - addition, multiplication
- bn254 field arithmetic
  - addition, multiplication, inversion
  - Montgomery reduction
- bn254 curve operations
  - point addition, inversion, scalar multiplication
- bn254 degree-2, degree-6, and degree-12 extensions
- bn254 pairings
  - constant vs variable inputs

## Complexity Analysis
- Proof size is about 300 bytes. The public inputs are roughly another 100 bytes.
- The maximum block size if 4 MB, so in theory, the size of assertTx and disproveTx may be almost up to 4 MB.
- Currently, a full block of space costs less than 0.3 BTC ~ $20000 in fees.
- Our current implementation of Winternitz signatures require about 31 bytes of overhead per bit of message. Thus, the assertTx may commit to up to 16 KB of trace data.
- A degree-12 extension field element is about 3 KB. Thus, naively, the assertTx may commit to up to 5 intermediate results.
- Thus, verifiers may choose from up 6 disproveTx Tapscripts, and the combined size of all Tapscripts is up to `6 x 4 MB = 24 MB`.


## General Ideas for Optimizations
- The prover can make another large commitment in his kickoffTx.
- We can use a sequence of commit transactions, effectively spreading out the commitment over multiple blocks.
- The chunks f1, f2, f3, ... don't have to be in sequence. Their inputs and outputs can form any kind of DAG. So we don't need to send global information along each step.
- The commitment script can make use of conditionals. E.g., "if z3 == 1 then commit to z11 else commit to z17"
- We can use hints / auxiliary inputs to the f_i / E.g., provide an inverse and then verify it using multiplication
- We can pre-parse script inputs into the right format. E.g., provide a value as bits on the stack instead of 30-bit limbs
- Wrap a STARK into a SNARK. One-time setup enabling fast and compact universal computation. E.g., RISC0:
  - [Bonsai](https://api.bonsai.xyz/swagger-ui/#/snark/route_snark_create)
  - [Local](https://github.com/risc0/risc0/tree/main/compact_proof)
- The disproveTx can be quite large because only a dishonest prover would have to pay for it
- We can hash intermediate results, compressing the assertTx, at the expense of having to compute a hash function in the disproveTx
