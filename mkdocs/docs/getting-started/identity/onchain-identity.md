# OnChain Identity

OnChain Identity is an identity that is controlled by a Smart Contract. It is a special case of Ethereum-controlled Identity.

The OnChain Identity manages its own identity trees on chain. It can issue credentials (by adding them to its claims tree), revoke them and perform state transitions.

## OnChain Issuer

And OnChain Issuer is a special case of OnChain Identity, which is used to issue credentials to other identities.

## Libraries and Contracts

* [OnChainIdentity.sol](https://github.com/iden3/contracts/blob/master/contracts/lib/OnChainIdentity.sol) - library that can create identity, manage trees, issue/revoke credentials and perform state transitions.
* [GenesisUtils.sol](https://github.com/iden3/contracts/blob/master/contracts/lib/GenesisUtils.sol) - library that can generate id from Ethereum address or identity state and verify it.
* [IdentityBase.sol](https://github.com/iden3/contracts/blob/master/contracts/lib/IdentityBase.sol) - base contracts to build OnChain Identity / Issuer Contracts with required public interfaces implemented.

## Benefits & Possible Use Cases

* Transparent and Auditable: smart contract code defines who can do what, e.g. who can issue credentials, who can rotate keys, etc.
* Trustless / Trust-Minimized (depending on smart contract business logic): no need to trust a third party to perform user verification correctly and issue credentials only to verified users. Correct behavior is enforced by the smart contract.
* Smart Governance: for example DAO may vote to issue credential (give executive/validator role) to a specific user, or to revoke credentials of a specific user. 
* Private and portable web3 reputation: think of proving balance, possession of NFTs or trade volumes without disclosing your address.
* Self-Issuance: user can go to the smart contract and issue herself a credential, that is valid and verifiable just like credentials issued by regular (off-chain) issuers.
* ZK-Self-Issuance: it's also possible to issue credentials with private web2 data. A user can create credentials on its own device and prove that it's created correctly and follows the rules of a Smart Contract and a specific ZK Circuit. For example, a user gets digitally signed data from its own biometric document, generates a verifiable credential out of it and proves that the resulting VC corresponds to the data, and data itself is properly signed with valid government keys. Then only the hash of the credential together with zero-knowledge proof is sent on-chain to be verified and added to OnChain Identity's Claims Tree. In this way, private data never leaves the user's device and it gets valid credential.
