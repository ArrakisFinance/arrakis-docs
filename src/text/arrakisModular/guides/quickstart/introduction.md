# TL;DR

An _Arrakis Modular Public Vault_ is an ERC20 Liquidity Provision Token, similar in spirit to Uniswap V2 LP tokens (but with more features under the hood).

### Add Liquidity

Depositors supply two-sided liquidity in the current asset ratio of the vault, minting an ERC20 LP receipt token. The vault's LP receipt token represents a claim on a proportion of the underlying vault assets, which are being supplied to a DEX liquidity pool under the hood.

### Hold LP Token

As usual, LP tokens have a claim on a _fluctuating amount_ of the two underlying assets deposited, since swappers trade against the liquidity on the DEX (given the rules and constraints of the DEX liquidity pool). One can think of holding an Arrakis Public Vault LP token as holding a share of a two-asset portfolio that has an active asset management strategy. You can track the underlying asset value of your LP token at every block.

### Remove Liquidity

LP token holders can burn the LP token at any time, to receive back their corresponding share of the vault's underlying two assets at that point in time.

