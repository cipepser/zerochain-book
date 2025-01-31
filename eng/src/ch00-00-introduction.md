# Introduction

This documentation helps developers understand the core concepts of Zerochain and walk through the steps required to build Zerochain's node and send confidential transaction using Zerochain’s module.

Zerochain is a generic privacy-protecting layer on top of Substrate. It provides some useful substrate modules and toolkit for protecting user's privacy and sensitive data which would be stored on chain.
Zerochain protocol(v1) itself takes a hybrid solutions with Zether, Zcash toolchain, and of course Substrate.
- Zether: High-level privacy scheme which takes an account-based approach
- Zcash toolchain: Basis Zero-knowledge proving system and elliptic curve operations
- Substrate: Core blockchain layer which provides P2P networking, database, consensus engine, etc...

<div align="center">
<img src="https://user-images.githubusercontent.com/20852667/59009598-33972d80-8869-11e9-922b-1f86e18455a8.png" width="500px">
</div>

The first goal for Zerochain is providing secure and efficient confidential/anonimous payment protocol for fungible assets. It means
- Transferred amounts are private
- Each account balance is private
- Identities of transactors are private

<div align="center">
<img src="https://user-images.githubusercontent.com/20852667/54678399-6d00ac80-4b48-11e9-9c8d-d1ec2b668761.png" width="500px">
</div>

Core features of Zerochain are following:
- Efficient computational cost of zk-proving and verifying
- Providing auditability for each account
- Storage friendly confidentiality from wallet and blockchain perspective

More precisely,
- Computational cost tends to be huge for zero-knowledge proving in general. Zerochain uses pre-processing zk-SNARKS which is kind of ZK proving systems and provides even small computational cost and proof size, there are some trade-off though.
- Statement in zk-SNARKs is based on Zether protocol so that prover computational cost is even less compairing other privacy-protecting protocols.
- Users can allow auditors to see how much they have balances by giving thier viewing key, but auditors cannot spend user's money by using it.
- Zerochain's wallet don't need to run either full node or light client. Simply, it can send transactions via RPC API.
- Zerochain is an account-based blockchain so it can avoid UTXO accumulation and save the growing storage.
