# SNARK Verifier in Bitcoin Script

A plan to implement a universal SNARK verifier in Bitcoin Script to run it in [BitVM2](/bitvm2).

## Possible Proof Systems
- Groth16
- FFlonk
- FFlonk + slonk

All three can operate over the bn254 curve.

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
