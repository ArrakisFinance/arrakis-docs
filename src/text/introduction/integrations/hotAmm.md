# HOT AMM

LPs are getting rekt by toxic order flow. HOT improves returns and maximizes capital efficiency for LPs, by internalizing MEV using an intent-based design.

HOT is a first of its kind hybrid AMM design, that combines the permissionless properties of AMMs with the capital efficiency and competitive pricing of a offchain RfQ system that attracts intents-based orderflow from solvers on intents protocols like CoWSwap and UniswapX.

HOT was designed by Arrakis and Valantis Labs. It is built on the [Valantis Modular DEX Framework](https://docs.valantis.xyz/). HOT is the first integration on Arrakis Modular and is powered by Arrakis's offchain market making infrastructure.

Just want to deposit? Here's our [New User Interface](https://app.arrakis.fi)

[See Details](../../arrakisModular/publicVaults.md#wethusdc-vault) of our flagship WETH/USDC public vault on Ethereum Mainnet which deploys liquidity into a HOT pool. This public vault offering combines a few advanced features under the hood: 
- actively managed concentrated liquidity rebalancing (via the Arrakis Public Vault `manager` role)
- intents-based Quoter activity (via the underlying HOT AMM `QuoteSigner` role)

Thanks to these roles (and proper strategies for their activity), LPs can passively make WETH/USDC markets in a way that is competitive with the most sophisticated Private Market Makers onchain.

To learn more, refer to the complete [HOT AMM section](../../modules/hotAmm/overview.md).
