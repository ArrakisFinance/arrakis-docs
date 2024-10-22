# Price Feeds

To accelerate the integration of public and private Meta Vaults LP tokens into DeFi applications, we have partnered with [Redstone](https://redstone.finance/).

## Methodology

Redstone provides customizable and safe price feeds for hundreds of tokens, which allows us to provide custom price feeds for Meta Vaults LP tokens. Both Pull and Push models are supported. We can construct the price feed as follows

1. Let `price0` and `price1` be the respective prices of `token0` and `token1` in USD, obtained from Redstone. If an USD price feed is not available but an ETH price feed is, we say `price0 = price0ETH * priceETHUSD / decimals`, where `decimals` is the precision of the `ETH` price feed (typically 8). Same for `price1`
2. Determine `reserve0` and `reserve1` of the two tokens in the vault by calling [`MetaVault::totalUnderlying()`](./technicalReference/metaVaults/core/abstract.ArrakisMetaVault.md#totalUnderlying)
3. Get the amount of decimals of each token `decimals0` and `decimals1`
4. Determine the total amount of `shares` of the vault by calling the standard ERC20 `MetaVault::totalSupply()`
5. If both price feeds use 8 decimals, the price in USD of `10^18` shares of the vault, with 8 decimals, is then given by

```
(reserve0 * price0 * 10 ** (18 - decimals0) +
    reserve1 * price1 * 10 ** (18 - decimals1)) / shares
```

NOTE: If price feeds have different amount of decimals, small adjustments are needed.
