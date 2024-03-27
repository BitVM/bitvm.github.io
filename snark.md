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
- bn254 degree-12 extension 
- bn254 pairings
  - constant vs variable inputs

## General Ideas for Optimizations
- The chunks f1, f2, f3, ... don't have to be in sequence. Their inputs and outputs can form any kind of DAG. So we don't need to send global information along each step.
- The commitment script can make use of conditionals. E.g., "if z3 == 1 then commit to z11 else commit to z17"
- We can use hints / auxiliary inputs to the f_i / E.g., provide an inverse and then verify it using multiplication
- We can pre-parse script inputs into the right format. E.g., provide a value as bits on the stack instead of 30-bit limbs
- Wrap a STARK into a SNARK. One-time setup enabling fast and compact universal computation. E.g., RISC0:
  - [Bonsai](https://api.bonsai.xyz/swagger-ui/#/snark/route_snark_create)
  - [Local](https://github.com/risc0/risc0/tree/main/compact_proof)
- The DisproveTx can be quite large because only a dishonest prover would have to pay for it
