# BitVM - Smarter Bitcoin Contracts

BitVM is a computing paradigm to express Turing-complete Bitcoin contracts. This requires no changes to the network’s consensus rules. Rather than executing computations on Bitcoin, they are merely verified, similarly to optimistic rollups. A prover makes a claim that a given function evaluates for some particular inputs to some specific output. If that claim is false, then the verifier can perform a succinct fraud proof and punish the prover. Using this mechanism, any computable function can be verified on Bitcoin.

## Ressources
- [BitVM whitepaper](bitvm.pdf)
- [BitVM Telegram group](https://t.me/bitVM_chat)
- [BitVM docs](https://github.com/BitVM/BitVM/docs)
- [BitVM organization on Github](https://github.com/BitVM)

### Presentations & Podcasts
- [Robin Linus and Lukas George at Bitcoin Amsterdam](https://www.youtube.com/watch?v=rubs5SrkGsM)
- [What is BitVM? with Robin Linus and Super Testnet (Stephan Livera Podcast)](https://www.youtube.com/watch?v=XxqQU6j6jI8)
- [Robin Linus at Brink Foundation](https://brink.dev/blog/2024/01/16/eng-call-bitvm/) ([slides](https://docs.google.com/presentation/d/12gHxC1bR6Nb7A5IzkRvIdw44l1zP1Tn1ea_DnTbA61Q/edit?usp=sharing))
- [Super Testnet's workshop "BitVM: Bitcoin Smart Contracts With Rich State"](https://www.youtube.com/watch?v=LwH9fhY4uGA)

## Implementation
- The [official BitVM implementation](https://github.com/BitVM/BitVM) in Rust
- The [initial draft implementation](https://github.com/BitVM/bitvm-js) in JavaScript

## Team
The project is lead by Robin Linus, the inventor of BitVM, together with the ZeroSync team, Lukas George and stillsaiko.
