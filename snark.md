# SNARK Verifier in Bitcoin Script

## Options
- Groth16
- FFlonk
- FFlonk + slonk

All three can operate over the bn254 curve.

## Code Modules 
- bn254 field arithmetic (addition, multiplication, inversion)
- bn254 curve operations (point addition, scalar multiplication)
- bn254 pairings
  - constants vs variable
- Lamport signatures / Winternitz signatures
