# Problem Statement

MEV losses are frequently associated with swappers because most retail DeFi users interact with DEXs to execute swaps. **But passive LPs collectively account for the biggest losses in today’s MEV landscape because they offer stale prices and lose out on fees to searchers, builders, and proposers** (and they need these fees to maintain profitability).

In the 2022 paper *Automated Market Making and Loss-Versus-Rebalancing,* Columbia University professor and a16z researcher Tim Roughgarden found that arbitrage costs ETH-USDC LPs about [11% of their principal per year](https://www.youtube.com/watch?v=q5vyJJb-Uyw).

Loss-Versus-Rebalancing is a term used to describe MEV lost through arbitrage as a result of LPs offering stale prices. As AMM prices update slower than CEXs, LPs become exposed to losses when arbitrageurs correct the discrepancy. LVR accounts for most MEV extraction on Ethereum.

The AMM space has evolved since MEV extraction started to encroach on DeFi. Uniswap V3 pioneered liquidity concentration to help LPs earn more fees but this feature requires active monitoring. **As MEV is brokered *offchain* through MEV-Boost, and most LPs passively provide liquidity *onchain*, LPs keep getting burned**.
