# Yield-bearing strategy

## Introduction

Yield-bearing tokens are crypto assets that automatically accrue interest or rewards over time, reflecting underlying yield-generating activities like lending or staking. Some examples include liquid staking tokens, vault shares of automated strategies, and tokenized real-world assets (RWAs) and TradFi instruments like treasury bonds or institutional loans.

While minting new yield-bearing tokens is usually possible in one single transaction, redeeming the underlying happens asyncrhronously, breaking the composability of this token. This can be solved by providing deep and consistent sell-side liquidity to AMMs. However, manual liquidity provisioning fails for this class of assets, whose price slowly drifts upward as yield accrues.

Our yield-bearing strategy leverages unique features of Uniswap V4 to ensure reliable liquidity for these tokens. This strategy can target up 99% of available liquidity on the sell side while avoiding price spikes in the AMM. It also embeds protections against price manipulations and depeg events where the yield becomes negative.

## Implementation

The yield-bearing strategy
