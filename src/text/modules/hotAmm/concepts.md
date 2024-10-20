# Concepts

### Hybrid Order Type

HOT is a first of its kind hybrid AMM design, that combines the permissionless properties of AMMs with the capital efficiency and non-toxic order flow of Private market making on intents-based protocols like CoWSwap and UniswapX.

HOT stands for Hybrid Order Type. HOT pools have two swap execution mechanisms that run in parallel: RfQ Quotes and Permissionless AMM.

### RfQ Quotes

- Solvers compete for non-toxic uninformed order flow from intents-based protocols (CoW Swap, UniswapX, 1inch Fusion etc).

- Permissioned solvers request quotes from an API, which calls the Arrakis offchain quoter and in turn issues quotes as a signed intent. Solvers can use these signed quotes at deterministic prices to fill their order against the HOT liquidity pool (until expiration).

- When executed, these signed quotes update the pool price playing a special role in keeping the price from becoming stale to mitigate against arbitrage.

Learn more about the Quoter [here](./quoter.md).

### Permissionless AMM

- A single concentrated liquidity position is used, akin to Uniswap v3. In addition a dynamic fee is implemented. Anyone can permissionlessly swap against the pool onchain by invoking the `swap` method.

- A dynamic fee that increases over time is used to further protect the pool against stale price arbitrage, in the event that a RfQ Quotes hasn’t been issued onchain recently. This fee is reset at the time a RfQ signed quoted is executed onchain.

### Arrakis Module

The only way to provide liquidity to a HOT pool is via an Arrakis Vault. The Vault exposes [Manager Functions](./manager.md) that the `manager` role can call to actively manage the Arrakis liquidity position in the pool.