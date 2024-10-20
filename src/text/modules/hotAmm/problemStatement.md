# Loss-Versus-Rebalancing (LVR)

### LVR Problem

MEV losses are frequently associated with swappers because most retail DeFi users interact with DEXs to execute swaps. **But passive LPs collectively account for the biggest losses in today’s MEV landscape because they offer stale prices and lose out on fees to searchers, builders, and proposers** (and they need these fees to maintain profitability). In the 2022 paper *Automated Market Making and Loss-Versus-Rebalancing,* Columbia University professor and a16z researcher Tim Roughgarden and his team found that arbitrage costs ETH-USDC LPs about [11% of their principal per year](https://www.youtube.com/watch?v=q5vyJJb-Uyw).

Loss-Versus-Rebalancing (LVR) is a term used to describe MEV lost through arbitrage as a result of AMMs offering LPs liquidity at stale prices. As AMM prices update slower than CEXs, LPs become exposed to losses when arbitrageurs correct the discrepancy. LVR accounts for a major part of MEV extraction on Ethereum.

The AMM space has evolved since MEV extraction started to encroach on DeFi. Uniswap V3 pioneered liquidity concentration to help LPs earn more fees but this feature requires active monitoring. **As MEV is brokered *offchain* through MEV-Boost, and most LPs passively provide liquidity *onchain*, LPs keep getting burned by LVR**.

### HOT AMM solution

HOT is an AMM design that attacks the LVR problem head on. It is done with a first of its kind Hybrid Order Type liquidity pool design. The summary for why it works well to recapture value for LPs is that an offchain API is trusted by the pool to issue signed orders to offchain swap requests at fair and competitive prices. 

This offchain RfQ is one of the two parallel order types that the HOT liquidity pool supports. RfQ sidesteps the LVR problem completely by handling pricing offchain (within some bounds of an onchain oracle check, for LP safety from a malicious quoter). 

For the classical AMM swap mode of the HOT liquidity pool, which is entirely onchain and thus subject to LVR, a combination of Dynamic Fees and injection of up-to-date info in RfQ swap execution both allow HOT to have more performant pricing than other onchain AMMs.
