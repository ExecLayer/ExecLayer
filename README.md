# ExecLayer

**Trustless Off-Chain Computation for Blockchain Smart Contracts**

ExecLayer is a decentralised computation layer that enables any smart contract on any blockchain to request the result of any algorithm — no matter how computationally expensive — and receive a fraud-proof-guaranteed answer without trusting a single operator.

---

## The Problem

Smart contracts face hard limits on computation. Solana's 1.4M Compute Unit ceiling, Ethereum's gas limits, and equivalent constraints on every other chain make it impossible to run sophisticated algorithms directly on-chain — options pricing, ML inference, multi-source data aggregation, and any iterative numerical method are all out of reach.

Existing workarounds (trusted operators, centralised servers, user-supplied results) all sacrifice either verifiability or decentralisation. ExecLayer solves both simultaneously.

---

## How It Works

ExecLayer separates **execution** from **verification**:

1. **Register** — Algorithm creators publish their algorithm (compiled to WASM) and register a compact cryptographic commitment on-chain. Only 32 bytes of storage required.
2. **Compute & Stake** — Provers execute the algorithm off-chain, submit their result on-chain, and back it with staked collateral.
3. **Verify or Challenge** — During a challenge window, anyone can dispute a result. An interactive bisection game narrows the disagreement through O(log n) rounds to a single disputed instruction, which is verified on-chain. The dishonest party loses their stake.

For a computation with 1 million steps, dispute resolution requires ~20 on-chain rounds. Only one WASM instruction is ever executed on-chain.

---

## Key Properties

- **Verifiable** — Every result is cryptographically committed. Fraud is detectable and punishable.
- **Permissionless** — Anyone can be a prover or challenger. No whitelists, no operators.
- **Chain-Agnostic** — Any smart contract on any blockchain can consume verified results.
- **Economically Secure** — Cheating is always more expensive than honest participation.
- **Minimal On-Chain Footprint** — Algorithm bytecode lives on IPFS. Only Merkle roots are stored on-chain.

---

## Main Repository Access

This repository is currently **private** as the project is in active research and development.

Access to the codebase can be granted upon request for:
- Researchers and academics working in related areas
- Grant reviewers and institutional partners
- Protocol teams interested in integration

To request access, please reach out via the contact details below.

---

## Research & Whitepaper

A public overview whitepaper is available in this repository -> [public whitepaper](https://github.com/ExecLayer/ExecLayer/blob/main/ExecLayer-Public-Whitepaper.pdf).

Website can be found at -> [execlayer.xyz](https://execlayer.xyz).

A comprehensive technical whitepaper detailing the protocol specification, security analysis, and implementation design is available upon request.

This project is conducted within the **EPFL Distributed Computing Laboratory (DCL)**

---

## Proof of Concept

A working prototype has been implemented and validated:

- Full WASM virtual machine capable of single-step proofs, implemented in Rust
- End-to-end bisection game protocol tested and working
- Black-Scholes options pricing formula successfully verified at ~890,000 WASM execution steps

---

## Links

| | |
|---|---|
| Website | [execlayer.xyz](https://execlayer.xyz) |
| Twitter / X | [@ExecLayer](https://twitter.com/ExecLayer) |
| Research Institution | [EPFL DCL](https://dcl.epfl.ch/site/) |
| Contact | alper.ozyurt@epfl.ch |

---

## Contact

**Alper Özyurt**  
BSc Computer Science, EPFL — MSc Computer Science, ETH Zurich (2026)  
Researcher & Engineer, ExecLayer  
[alper.ozyurt@epfl.ch](mailto:alper.ozyurt@epfl.ch) · [LinkedIn](https://www.linkedin.com/in/alper-özyurt-985683230/)

---

*ExecLayer is an active research project. This is not a production-ready system. Protocol specifications and implementation details are subject to change.*
