# BitVM - Smarter Bitcoin Contracts

BitVM enables a free market of second layers, potentially scaling Bitcoin to billions of users.

## Intro
BitVM is a computing paradigm to express Turing-complete Bitcoin contracts. This requires no changes to the network’s consensus rules. Rather than executing computations on Bitcoin, they are merely verified, similarly to optimistic rollups. A prover makes a claim that a given function evaluates for some particular inputs to some specific output. If that claim is false, anyone can perform a fraud proof and punish the prover. Using this mechanism, any computable function can be verified on Bitcoin.

BitVM is the foundational element to bridge BTC to second layers such as sidechains, rollups, and [zkCoins](https://gist.github.com/RobinLinus/d036511015caea5a28514259a1bab119).

## Implementation
- The [official BitVM implementation](https://github.com/BitVM/BitVM) in Rust
- [Developer Preview](./demo/)


## Resources
- [Bitvm3s](bitvm3.pdf)
- [BitVM3-RSA (broken)](bitvm3-rsa.pdf)
- [BitVM Bridge](https://bitvm.org/bitvm_bridge.pdf)
- [BitVM 2 writeup](./bitvm2)
- [BitVM whitepaper](bitvm.pdf)
- [BitVM Telegram group](https://t.me/bitVM_chat)
- [BitVM docs](https://github.com/BitVM/BitVM/tree/1dce989d1963b90c35391b77b451c6823302d503/bitvm/docs)
- [BitVM organization on Github](https://github.com/BitVM)
- [Tree++ overview](treeplusplus.md)
- [Awesome BitVM](https://github.com/Rsync25/awesome-bitvm)

### Presentations & Podcasts
- [Robin Linus and Lukas George at Bitcoin Amsterdam](https://www.youtube.com/watch?v=rubs5SrkGsM)
- [What is BitVM? with Robin Linus and Super Testnet (Stephan Livera Podcast)](https://www.youtube.com/watch?v=XxqQU6j6jI8)
- [Robin Linus at Brink Foundation](https://brink.dev/blog/2024/01/16/eng-call-bitvm)
- [Super Testnet's workshop "BitVM: Bitcoin Smart Contracts With Rich State"](https://www.youtube.com/watch?v=LwH9fhY4uGA)
- [Deep dive into the draft implementation](https://www.youtube.com/watch?v=7sRqzoZorn0)
- [Robin Linus at BitDevs meetup at Stanford (slides only)](https://docs.google.com/presentation/d/12gHxC1bR6Nb7A5IzkRvIdw44l1zP1Tn1ea_DnTbA61Q/edit?usp=sharing)
- [BitVM: Smarter Bitcoin Contracts at ZKProof in Berlin](https://www.youtube.com/live/VIg7BjX_lJw)
- [Introducing BitVM at MIT Bitcoin Expo 2024](https://www.youtube.com/watch?v=nhR_g9hPnqM)


## About BitVM Alliance

The BitVM Alliance was founded by Robin Linus and Lukas George to accelerate the development and implementation of BitVM project. This strategic partnership brings together leading projects and teams dedicated to advancing BitVM development.

By combining expertise and resources, the alliance aims to expedite the delivery of the first BitVM bridges while ensuring robust security and innovative solutions. The collaborative nature of the alliance enables rapid knowledge sharing, coordinated development efforts, and comprehensive peer review of critical components.

Current members of the BitVM Alliance include (in alphabetical order):

- [Alpen](https://x.com/AlpenLabs)
- [Babylon](https://x.com/babylonlabs_io)
- [Bitlayer](https://x.com/BitlayerLabs)
- [BOB](https://x.com/build_on_bob)
- [Citrea](https://x.com/citrea_xyz)
- [Element](https://x.com/element_labs42)
- [Fiamma](https://x.com/fiamma_labs)
- [GOAT network](https://www.goat.network)
- [ZeroSync](https://x.com/ZeroSync_)


## Contributors
The BitVM project is lead by its inventor, [Robin Linus](https://robinlinus.com), together with Lukas George and Stillsaiko. Special thanks to Super Testnet, Carsten Munk, Hakan Karakuş, Weikeng Chen, and Steven Roose for their code contributions. We're also collaborating in research projects together with Liam Eagen, Alexei Zamyatin, Distributed Lab, as well as Matteo Maffei's and Zeta Avarikioti's group at TU Vienna, and David Tse's group at Stanford.

BitVM is developed as free and open source software under the umbrella of the [ZeroSync](https://zerosync.org) nonprofit organization. It is funded by research grants from Spiral, Starkware, OpenSats, and community contributions.

### Want to Contribute?
- Join the [Telegram group](https://t.me/bitVM_chat)
