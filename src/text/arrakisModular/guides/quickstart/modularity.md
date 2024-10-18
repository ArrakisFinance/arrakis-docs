# Modularity

The beauty of an _Arrakis Modular Vault_ is that the complexities of LPing into any specific DEX (interfaces, LP decision space, quirks) can be abstracted away from depositors. For instance, every Public Vault has the same, simple UniswapV2-style LP experience, where LPs only make decisions about when and how much liquidity to provide or withdraw.

To the uncurious who do not care to know how the liquidity is actively managed or even what DEX the liquidity is being supplied to, a vault can be a black box. Holders can simply track the returns of their underlying.

For the curious or those doing their diligence, Public Vaults have configurable modules and management parameters that can be inspected onchain to understand the exact details of how the vault functions, and how changes to this functionality are governed.

[See Here](../../publicVaults.md) for information on the configuration of a Live Public Vault

[See Here](../../architecture/configuration.md) to learn more about vault configurability

**All Public Vault ownership is behind a multi-day timelock so that LPs are guaranteed to have time to react to any changes in onchain configuration.**
