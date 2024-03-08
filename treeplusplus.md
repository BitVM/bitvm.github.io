# Tree++ 
Tree++ is a language for smarter Bitcoin contracts. 

## Advanced Scripting
At the core of Tree++ there is a templating language which can express complex Bitcoin Scripts.

- Evaluate constant expressions
- Parametrized templates
- Unroll loops
- Compose opcodes
- Library of composed opcodes
  - E.g., multiplication, bitwise XOR, bitwise shifts, blake3,...
- Statefulness
  - Lamport signatures (message sizes: u8, u32, u160, ...)
  - Also Winternitz signatures
  - In the future maybe OP_CHECKSIGFROMSTACK

## Graphs of Transactions
- Compose Tree++ scripts into potentially large Taptrees
- Model contract logic in form of graphs of transactions
- Statefulness
  - presigning
  - connector outputs
