# Modularity

The beauty of an _Arrakis Modular Public Vault_ is that the specific complexities of providing liquidity to a DEX (interfaces, LP decision space, quirks) can be abstracted away entirely. Every Public Vault has the same simple UniswapV2-style LP experience, where LPs only make decisions about when and how much liquidity to provide or withdraw.

To an uncurious depositor who does not care to know how the liquidity is actively managed or even what DEX the liquidity is being supplied to, vault functionality can be a black box. These holders can simply track the returns of their underlying. 

For the curious and diligent, Public Vaults have configurable modules and managemnet parameters that can be inspected onchain to understand the exact details of how the vault functions.


[See Here](../../publicVaults.md) for information on the configuration of a Live Public Vault

[See Here](../../architecture/configuration.md) to learn more about vault configurability

**All Public Vault ownership is behind a multi-day timelock so that LPs are guaranteed to have time to react to any changes in onchain configuration.**
