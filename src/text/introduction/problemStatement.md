# Problem Statement

As Ethereum has grown, sophisticated actors have infiltrated DeFi using complex strategies and sophisiticated offchain infrastructure to extract value from Ethereum.

## Centralised Vertically-integrated Market Makers (CVMMs) Taking Over DeFi
We define CVMMs as sophisticated centralised actors who simultaneously participate in block building, MEV extraction, private order flow and most recently, capturing volumes via private market makers (PMMs). In other words, trading firms like Wintermute.

CVMMs extract the majority of profits from onchain liquidity, leaving protocols and liquidity providers to fight for toxic order flow. As of Oct 2024, Token Issuers, Retail DeFi, and other LPs have leaked $800M in MEV to poorly designed AMMs since the merge (Oct 2022).

Before Intent protocols like UniswapX, CoWSwap and 1inch Fusion emerged, CVMMs primarily focused on extracting value from passive LPs and onchain traders by channeling MEV and arbitrage strategies through their own block builders. 

## The Rise of Intents Protocols
UniswapX, CoWSwap and 1inch Fusion account for more than 50% of all trades on Ethereum, as of October 2024 ([link](https://dune.com/queries/3146796/5248450)). As intents have gained pace, these actors have started to monopolize DeFi, leaving LPs with less revenue and more exposure to toxic flow.

Intents Protocols have disrupted the onchain trading landscape. While they might offer swappers better pricing in the short-term, they exacerbate losses for passive LPs who are now left behind with less healthy flow from noise trading and a higher relative quantity of toxic, arbitrage-laden order flow. How so? Intent protocols offer CVMMs the ability to fill non-toxic order flow on their own private inventory via proprietary and highly sophisticated RFQ systems, which passive LPs cannot compete with.

But even swappers will be hurt in the long-term. As highlighted in the excellent paper titled [Illuminating Ethereum's Order FLow Landscape](https://writings.flashbots.net/illuminate-the-order-flow) by the Flashbots team:
- Order from retail users is being segmentation away from passive LPs to a permissioned set of market makers
- This in turn drives power to the hands of a few actor, creating a winner-takes-all dynamic
- Ove the long-term, even swappers will be hurt as powerful actors dictate liquidity provision.

In short, the designs of intents could even threaten the very decentralised nature of Ethereum by giving power to a few powerful actors. We shouldn't repeat the same mistakes from TradFi where extractive market makers take the lions share of profits.

## Long Tail Liquidity
Furthermore, CVMMs are poorly equipped to cater to longtail assets, which will become a bigger problem as more of the world’s value moves onchain. 

CVMMs cannot service the entire long tail of tokens since they lack the inventory and operational scale. This results in the long-tail market being underserved, not benefiting from the improved pricing and capital efficiency that PMMs have provided to blue chips. The vast majority of these tokens are highly illiquid and mostly operate on legacy DEX infrastructure.

## Where Arrakis Fits in
Arrakis is focused on being a decentralized **onchain market making** solution, with a key feature of built-in MEV-Awareness / vertical integration into the MEV supply chain. By recapturing value to the application layer, Arrakis protects token issuers and LPs capital and increases their profitability.

Arrakis is building the first decentralised vertically-integrated market making solution.

> The liquidity must flow.