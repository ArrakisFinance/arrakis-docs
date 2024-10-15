# Quoter

A crucial offchain component of the HOT AMM is the `QuoteSigner` role which is set directly on the `HOT.sol` smart contract containing the core liquidity pool logic of the HOT AMM.

Whoever holds the private key to the `QuoteSigner` role has the authority to issue signed quotes that allow recipients to execute swaps directly against the funds in the liquidity pool at the prices determined in the signed quotes (subject to certain onchain safety checks on the price and volume of the quotes).

For Arrakis Public Vaults, the _Quoter_ is a semi-trusted automated offchain process, which escrows the Public Vault `QuoteSigner` key and signs quotes to integrated parties (like CoWSwap solvers) at prices determined by the state of centralized exchanges, state of the LP Vault's onchain reserves, and the current Requests-For-Quotes from outside parties like solvers.

## Quoter Market Making Strategy

The Public Vault Quoter uses an Avellaneda and Stoikov based approach to RfQ market making, where the goal is to converge to a target inventory ratio (e.g. the active ETH/USDC mainnet Public Vault targets a 50/50 inventory ratio).

Taking into account the current centralized exchange prices and curent orderflow, the quoter determines a robust market mid price at, as well as an estimate of the asset's volatility, at any time t. With the mid price and volatility, as well as the skew of the Vault inventory from the target ratio, the Avellaneda and Stoikov market making algorithm determines a best bid and ask for any time t that it is willing to accept. This is the criteria the Quoter uses for determining if we will sign requests from solvers for execution at or better than the desired prices in their requests.

## Quoter Oracle Values

When the `QuoteSigner` issues signed quotes they can attach metadata that acts as oracle values to the state of the onchain AMM if and when the quote gets executed onchain. The key values are:

- a new value for the midprice of the AMM, based on the Quoter's current instantaneous midprice observed offchain (`sqrtSpotPriceX96New`)
- a new starting value for swap fee rates (`feeMinToken{0,1}`)
- a new growth rate for swap fees (`feeGrowthE6Token{0,1}`)
- a new max swap fee for the fee growth to stop at (`feeMaxToken{0,1}`)

When one of these RfQ quotes actually executes onchain (and is the first one to do so in a block) it will automagically reset the state of the AMM from that point in the block onward to:

- spot price at `sqrtSpotPriceX96New`
- swap fee for token{0,1} of `feeMinToken{0,1} + feeGrowthE6Token{0,1} * (blockTimestamp- signatureTimestamp) / 100` (the minimum fee, plus the growth rate for the amount of time that has elapsed since this quote was signed)

If no new signed quotes land at the top of the next block then the swap fee rates will continue to grow second by second at the linear rate and thus will be larger at the top of the next block. This swap fee growth continues until the fee hits the maximum rate or until a new signed quote lands and resets the process.

## Quoter Decentralization

One major direction of research and development at Arrakis is to make the _Quoter_ more transparently verifiable and trustless rather than make it a semi-trusted central point of failure for Arrakis Public Vaults.