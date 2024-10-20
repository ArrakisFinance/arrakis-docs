# HOT AMM

LPs are getting rekt by toxic order flow. HOT improves returns and maximizes capital efficiency for LPs, by internalizing MEV using an intent-based design.

To learn more, refer to the complete [HOT AMM section](../../modules/hotAmm/overview.md).

Just want to deposit? Here's our [New User Interface](https://app.arrakis.fi)

HOT was designed by Arrakis and Valantis Labs. It is built on the [Valantis Modular DEX Framework](https://docs.valantis.xyz/). HOT is the first integration on Arrakis Modular and is powered by Arrakis's offchain market making infrastructure.

Our flagship WETH/USDC public Arrakis Modular vault on Ethereum Mainnet deploys liquidity into a HOT AMM pool ([details](../../arrakisModular/publicVaults.md#wethusdc-vault)). 

This public vault offering is similar to LPing on a traditional AMM, but has a few advanced features under the hood: 
- actively managed concentrated liquidity rebalancing (via the Arrakis Public Vault `manager` role)
- intents-based Quoter activity (via the underlying HOT AMM `QuoteSigner` role)

Thanks to these roles (and proper strategies for their activity), LPs can passively make WETH/USDC markets in a way that is competitive with the most sophisticated Private Market Makers onchain.
