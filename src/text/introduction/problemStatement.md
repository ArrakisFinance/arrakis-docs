# Problem Statement

As Ethereum has grown, sophisticated actors have infiltrated DeFi using complex strategies and sophisiticated offchain infrastructure to extract value from Ethereum.

## Centralised Vertically-integrated Market Makers (CVMMs)
We define CVMMs as sophisticated centralised actors who simultaneously participate in block building, MEV extraction, private order flow and most recently, capturing volumes via private market makers (PMMs). In other words, trading firms like Wintermute.

CVMMs extract the majority of profits from onchain liquidity, leaving protocols and liquidity providers to fight for toxic order flow. As of Oct 2024, Token Issuers, Retail DeFi, and other LPs have leaked $800M in MEV to poorly designed AMMs since the merge (Oct 2022).

Before Intent protocols like CoW Swap, 1inch Fusion and UniswapX emerged, CVMMs primarily focused on extracting value from passive LPs and onchain traders by channeling MEV and arbitrage strategies through their own block builders. 

## The Rise of Intents Protocols
Uniswap X, CoW Swap and 1inch fusion account for more than 50% of all trades on Ethereum, as of October 2024 ([link](https://dune.com/queries/3146796/5248450)). As intents have gained pace, these actors have started to monopolize DeFi, leaving LPs with less revenue and more exposure to toxic flow.

Intents Protocols have disrupted the onchain trading landscape. While they might offer swappers better pricing, they exacerbate losses for passive LPs who are now left behind with less healthy flow from noise trading and a higher relative quantity of toxic, arbitrage-laden order flow. How so? Intent protocols offer CVMMs the ability to fill non-toxic order flow on their own private inventory via proprietary and highly sophisticated RFQ systems. 

## Long Tail Liquidity
Furthermore, CVMMs are poorly equipped to cater to longtail assets, which will become a bigger problem as more of the world’s value moves onchain. 

CVMMs cannot service the entire long tail of tokens since they lack the inventory and operational scale. This results in the long-tail market being underserved, not benefiting from the improved pricing and capital efficiency that PMMs have provided to blue chips. The vast majority of these tokens are highly illiquid and mostly operate on legacy DEX infrastructure.

## Where Arrakis Fits in
Arrakis is focused on being a decentralized **onchain market making** solution, with a key feature of built-in MEV-Awareness / vertical integration into the MEV supply chain. By recapturing value to the application layer, Arrakis protects token issuers and LPs capital and increases their profitability.

> The liquidity must flow.