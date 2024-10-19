# HOT AMM

LPs are getting rekt by toxic order flow. HOT improves returns and maximizes capital efficiency for LPs, by internalizing MEV using an intent-based design.

HOT is a first of its kind hybrid AMM design, that combines the permissionless properties of AMMs with the capital efficiency and competitive pricing of a permissioned RfQ system for that attracts intents based order flow from solvers on intents protocols like CoWSwap and UniswapX.

HOT AMM is the first underlying DEX to be integrated into Arrakis Modular. [See Details]() of our flagship Public WETH/USDC vault on Ethereum Mainnet which deploys liquidity into HOT AMM.

Read the [Problem Statement]() that galvanizes the creation of HOT AMM

Just want to deposit? Here's our [New User Interface]()

## How HOT AMM works

HOT was designed by Arrakis and Valantis Labs. It is built on the [Valantis Modular DEX Framework](https://docs.valantis.xyz/). HOT is the first integration on Arrakis Modular and is powered by Arrakis's offchain market making infrastructure.

HOT pools have two swap execution mechanisms:

### RfQ Quotes

- Solvers compete for non-toxic uninformed order flow from intents protocols like CoW Swap, Uniswap X and 1inch Fusion.
- Solvers ping an offchain api to get a quote from the HOT AMM [Quoter]() at a competitive and deterministic price.
- Solvers Execute valid signed quotes directly against the AMM reserves to complete their swaps (at the price determined in the quote, regardless of AMM state)
- Signed RfQ-quotes also attach trusted metatdata, when quotes execute this metadata is used to refresh AMM state and boost the performance of the permissionless AMM.

### Permissionless AMM

- Anyone can swap against the AMM which is akin to Uniswap v3. A dynamic swap fee mechanism is added to traditional concentrated liquidity.
- The linearly increasing dynamic fee (up to a max) protects the pool against stale price arbitrage, in the event that an RfQ Quote hasn’t been issued onchain recently. Fees reset to a lower value at the time a RfQ signed quoted is executed onchain, restarting the process.

To learn more, refer to the complete [HOT AMM section](../../modules/hotAmm/overview.md).
