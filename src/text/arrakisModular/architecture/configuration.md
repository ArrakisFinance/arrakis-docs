# Meta Vault Configuration

Every Meta Vault has configurable components which can be adjusted by the vault Owner role. The key configurables are:

- _whitelisted modules_: a set of contracts which each define a type of integration with an underlying liquidity protocol (e.g. HOT AMM module) and each expose certain liquidity management functions that can be invoked by the manager.
- _active module_: the currently active module from the whitelisted set.
- _manager config_: set on the _Arrakis Standard Manager_ this struct defines an `executor` who can call liquidity management functions for this vault from offchain, and defines safety checks on any liquidity management actions that the `executor` invokes.

### Configuration Management

The _Arrakis Modular Public Vault_ owner role (Arrakis DAO, currently controlled by MultiSig) has the ability to whitelist _modules_ and configure management parameters on the _Arrakis Standard Manager_ to augment where Public Vault liquidity flows and how it behaves. This way Arrakis Public Vaults can stay up to date with the most competitive liquidity provision venues and strategies onchain.

### Vault Owner Role

**All Public Vault ownership is immutably behind a multi-day timelock so that LPs are guaranteed to have time to react to any changes in configuration.**

Private Vaults Ownership is mapped in the Private Vault NFT contract, and Private Vaults do not enforce a timelock on vault ownership (this is because private vault owners and liquidity providers are expected to be the same user/entity).