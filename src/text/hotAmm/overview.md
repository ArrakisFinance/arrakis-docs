# Overview

HOT is an AMM providing optimized returns for LPs and token issuers through a first of its kind intents-aligned approach to on chain liquidity.

HOT is the first DEX integrated into the new version of the Arrakis Protocol (Arrakis Modular) and the first DEX to exist on top of Valantis Lab’s Sovereign Pools which are a modular generalization of DEX architectures, allowing for non-fragmented liquidity across a composable system of pools and modules.

HOT stands for Hybrid Order Type. HOT pools have two swap execution mechanisms:

- RfQ Quotes
- Permissionless AMM

RfQ Quotes:

- Permissioned solvers request quotes from an API, which calls the Arrakis quoter in turn issuing quotes as a signed intent. Solvers can use these signed quotes to fill order from the liquidity pool before the quotes expire.
- When executed, these signed quotes update the pool price playing a special role in keeping the price from becoming stale to mitigate against arbitrage.

Permissionless AMM:

- A single concentrated liquidity position is used, akin to Uniswap v3. In addition a dynamic fee is implemented.
- A dynamic fee that increases over time is used to further protect the pool against stale price arbitrage, in the event that a RfQ Quotes hasn’t been issued onchain recently. This fee is reset at the time a RfQ signed quoted is executed onchain.

Benefits to LPs:

- Attract non-toxic order flow from intents protocols like CoW Swap, Uniswap X and 1inch Fusion.
- LPs will receive more flow that would have otherwise gone to a Private Market Maker like Wintermute (not to a regular AMM).

Benefits to solvers:

- Receive a deterministic quote at a competitive price
