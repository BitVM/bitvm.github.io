# SNARK Verifier in Bitcoin Script

A plan to implement a SNARK verifier in Bitcoin Script to run it in [BitVM2](/bitvm2.md).

## Bitcoin Script Constraints

### Fundamental Constraints
- Max script size: 4 MB
- Max stack size: altstack + stack < 1000 items 
- Max stack item size: 520 bytes
- Max input size for arithmetic opcodes: 32-bit words

### Practical Constraints
- Max script input in form of 32-bit words: `1000 items * 32-bit/item = 32 kB`
- Overhead of transferring state between Scripts
  - 26 bytes per bit (using Winternitz signatures)
  - 1 stack item for every 4 bits (each item 20 bytes)
  - Maximum input state size per Script: `1000 items * 4 bit/item = 4000 bits = 500 bytes` (requires 20 kB of signature data)


## Possible Proof Systems
- Groth16 ( 22000 Fq multiplications )
- [FFlonk](https://eprint.iacr.org/2021/1167) ( 14000 Fq multiplications + hash function )
- FFlonk + slonk

All three can operate over the bn254 curve.

Example implementations:
- [Arkworks](https://github.com/arkworks-rs/groth16)
- [snarkjs](https://github.com/iden3/snarkjs)


## Code Modules 
- Lamport signatures / Winternitz signatures
- u256 arithmetic
  - addition, multiplication, Karatsuba multiplication
- bn254 field arithmetic
  - addition, multiplication, inversion
  - Montgomery reduction
- bn254 curve operations
  - point addition, inversion, scalar multiplication
- bn254 degree-2, degree-6, and degree-12 extensions
- bn254 pairings
  - constant vs variable inputs

## Complexity Analysis
- The Groth16 Proof size is about 300 bytes. The public inputs are roughly another 100 bytes.
- Currently, a full block of space costs less than 0.3 BTC ~ $20000 in fees.
- The assertTx may commit to up to 16 KB of trace data.
- A degree-12 extension field element is about 3 KB. Thus, naively, the assertTx may commit to only about 5 intermediate results. Verifiers could choose only from up 6 disproveTx Tapscripts, and the combined size of all Tapscripts is up to `6 x 4 MB = 24 MB`. Using hash commitments, we can compress the signatures commitments at the expense of more overhead in the disprove scripts.
  - A full block can commit to about `4 MB / block * 26 bytes / bit = 16 kB / block` of signed data.
  - That's about `( (4mb / 26 byte) bits ) / 20 bytes = 960` 20-byte hashes. Thus, we could chunk the computation into about 960 Scripts of 4 MB each. Considering a communication overhead of about 1-2 MB, we can run computations of up to 2 to 4 GB in total.



## General Ideas for Optimizations
- The prover can make another large commitment in his kickoffTx.
- We can use a sequence of commit transactions, effectively spreading out the commitment over multiple blocks.
- The chunks f1, f2, f3, ... don't have to be in sequence. Their inputs and outputs can form any kind of DAG. So we don't need to send global information along each step.
- The commitment script can make use of conditionals. E.g., "if z3 == 1 then commit to z11 else commit to z17"
- We can use hints / auxiliary inputs to the f_i / E.g., provide an inverse and then verify it using multiplication
- We can pre-parse script inputs into the right format. E.g., provide a value as bits on the stack instead of 30-bit limbs
- Wrap a STARK into a SNARK. One-time setup enabling fast and compact universal computation.
  - E.g., RISC0: [Bonsai](https://api.bonsai.xyz/swagger-ui/#/snark/route_snark_create) and [Local](https://github.com/risc0/risc0/tree/main/compact_proof)
- The disproveTx can be quite large because only a dishonest prover would have to pay for it
- We can hash intermediate results, compressing the assertTx, at the expense of having to compute a hash function in the disproveTx
