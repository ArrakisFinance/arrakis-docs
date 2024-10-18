# TL;DR

An _Arrakis Modular Public Vault_ is a two-sided LP token, similar in spirit to Uniswap V2 LP tokens (but with more going on under the hood).

### Add Liquidity

Depositors supply two-sided liquidity in the current asset ratio of the vault, minting an ERC20 LP receipt token. The vault's LP receipt token represents a claim on a proportion of the underlying vault assets. Under the hood, the vault seamlessly supplys these assets to a DEX liquidity pool.

### Hold LP Token

As usual, LP tokens have a claim on a _fluctuating amount_ of the two underlying assets deposited, since swappers trade against the liquidity on the DEX (given the rules and constraints of the DEX liquidity pool). You can track the underlying asset value (including fees earned) of your LP token at every block.

### Remove Liquidity

LP token holders can burn the LP token at any time, to receive back their corresponding share of the vault's underlying two assets at that point in time.

