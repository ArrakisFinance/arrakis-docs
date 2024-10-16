# HOT AMM

LPs are getting rekt by toxic order flow. HOT improves returns and maximizes capital efficiency for LPs, by internalizing MEV using an intent-based design.

HOT is a first of it's kind hybrid AMM design, that combines the permissionless properties of AMMs with the capital efficiency and non-toxic order flow of intents protocols.

## Problem Statement

### LPs bear the high cost of rebalancing AMMs
By design, AMMs 'pay' arbitrageurs to rebalance pools. In the 2022 paper *Automated Market Making and Loss-Versus-Rebalancing,* Columbia University professor and a16z researcher Tim Roughgarden found that arbitrage costs ETH-USDC LPs about [11% of their principal per year](https://www.youtube.com/watch?v=q5vyJJb-Uyw).

### The rise of intents protocols has spawned a new class of centralised actors
An unintended consequence of intents protocols is that they have birthed a new class of liquidity provider called the "Centralised Vertically-integrated Market Maker" (CVMM).

### Good flow to centralised actors and toxic order flow to AMMs
The sophisticated offchain infrastructure of CVMMs gives them an unfair advantage over passive LPs. LPs are left to compete for toxic order flow, driving passive LPs close to extinction.


## How HOT AMM works
HOT was designed by Arrakis and Valantis Labs. It is built on the [Valantis Modular DEX Framework](https://docs.valantis.xyz/). HOT is the first integration on Arrakis Modular and is powered by Arrakis's offchain market making infrastructure.

HOT pools have two swap execution mechanisms:

### RfQ Quotes
- Solvers compete for non-toxic uninformed order flow from intents protocols like CoW Swap, Uniswap X and 1inch Fusion. 
- In turn these solvers update the pool price.

### Permissionless AMM
- Anyone can swap against the AMM which is akin to Uniswap v3. In addition a dynamic fee is implemented.
- A dynamic fee that increases over time is used to further protect the pool against stale price arbitrage, in the event that a RfQ Quotes hasn’t been issued onchain recently. This fee is reset at the time a RfQ signed quoted is executed onchain.

You go to the [HOT AMM section](/src/text/hotAmm/overview.md) to learn more.
