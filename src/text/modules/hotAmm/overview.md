# HOT AMM Overview

## TL;DR

LPs are getting rekt by toxic order flow. HOT improves returns and maximizes capital efficiency for LPs, by internalizing MEV using an intent-based design.

HOT was designed by Arrakis and Valantis Labs. It is built on the [Valantis Modular DEX Framework](https://docs.valantis.xyz/). HOT is the first integration on Arrakis Modular and is powered by Arrakis's offchain market making infrastructure.

## Hybrid Order Type

HOT is a first of its kind hybrid AMM design, that combines the permissionless properties of AMMs with the capital efficiency and non-toxic order flow of intents protocols.

HOT stands for Hybrid Order Type. HOT pools have two swap execution mechanisms:

- RfQ Quotes
- Permissionless AMM

### RfQ Quotes

- Solvers compete for non-toxic uninformed order flow from intents protocols like CoW Swap, Uniswap X and 1inch Fusion.
- Permissioned solvers request quotes from an API, which calls the Arrakis off chain quoter and in turn issuing quotes as a signed intent. Solvers can use these signed quotes to fill order from the liquidity pool before the quotes expire.
- When executed, these signed quotes update the pool price playing a special role in keeping the price from becoming stale to mitigate against arbitrage.

### Permissionless AMM

- A single concentrated liquidity position is used, akin to Uniswap v3. In addition a dynamic fee is implemented.
- A dynamic fee that increases over time is used to further protect the pool against stale price arbitrage, in the event that a RfQ Quotes hasn’t been issued onchain recently. This fee is reset at the time a RfQ signed quoted is executed onchain.
