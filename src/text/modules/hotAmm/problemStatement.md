# Problem Statement

## Intro
MEV losses are frequently associated with swappers because most retail DeFi users interact with DEXs to execute swaps. **But passive LPs collectively account for the biggest losses in today’s MEV landscape because they offer stale prices and lose out on fees to searchers, builders, and proposers** (and they need these fees to maintain profitability). In the 2022 paper *Automated Market Making and Loss-Versus-Rebalancing,* Columbia University professor and a16z researcher Tim Roughgarden found that arbitrage costs ETH-USDC LPs about [11% of their principal per year](https://www.youtube.com/watch?v=q5vyJJb-Uyw).

Loss-Versus-Rebalancing is a term used to describe MEV lost through arbitrage as a result of LPs offering stale prices. As AMM prices update slower than CEXs, LPs become exposed to losses when arbitrageurs correct the discrepancy. LVR accounts for most MEV extraction on Ethereum.

The AMM space has evolved since MEV extraction started to encroach on DeFi. Uniswap V3 pioneered liquidity concentration to help LPs earn more fees but this feature requires active monitoring. **As MEV is brokered *offchain* through MEV-Boost, and most LPs passively provide liquidity *onchain*, LPs keep getting burned**.

## Loss-Versus-Rebalancing

HOT AMM takes two approaches to make LPing more sustainable: LVR reduction and LVR mitigation. 

### LVR reduction
With signed quotes, HOT directly reduces LVR by offering guaranteed prices for liquidity. The Arrakis Quoting Service uses an offchain component to establish a fair price for each trade, which minimizes losses for LPs. This service also offers solvers favorable quotes whenever the pool needs rebalancing to reduce LVR. With this system, solvers unlock the liquidity at the quoted price, the quotes minimize losses for LPs, and LPs get more healthy volume. 

### LVR mitigation
HOT also mitigates LVR with a dynamic fee model. Fees increase until a new swap and solver update resets prices. This means prices have less time to deviate from the market price and profiting from arbitrage is harder because fees increase with time. Where arbitrageurs aim to profit from volatility, dynamic fees prevent arbitrage by putting a higher price on volatility than a traditional AMM with a static fee. 

## Benefits for LPs
- **Decreased LVR and increased healthy flow**: Solvers pass non-toxic, uninformed order flow that mitigates Loss-Versus-Rebalancing (LVR).
- **Protection against stale price arbitrage**: HOT's dynamic fee increases as price becomes more stale protecting users against arbitrage related MEV. HOT's dynamic fee increases as price becomes more stale protecting users against arbitrage related MEV. 
- **High capital efficiency**: The solver order flow to HOT's RFQ/PMM side can achieve high volume to TVL multiples. 

## Benefits for solvers:
- Receive a deterministic quote at a competitive price


