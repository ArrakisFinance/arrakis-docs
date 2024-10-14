# Concepts

The HOT AMM is a new type of liquidity pool with advanced functionalities; however, for depositor LPs into Arrakis Modular Public Vaults the experience is very similar to LPing in a traditional AMM or in any Arrakis Public Vault.

## Public Vault Depositor

Depositors supply two-sided liquidity in the current asset ratio of the Public Vault, minting an ERC20 LP receipt token. The vault's LP receipt token represents a claim on a proportion of the underlying vault assets which are being supplied to a DEX liquidity pool under the hood. LP tokens have a claim on a _fluctuating amount_ of the two deposited assets, since swappers trade against the tokens in the liquidity pool (given the rules and constraints of the pool). LP token holders can burn these tokens at any time, to execute the claim and receive back the corresponding share of the vault's underlying two tokens at that time.

At this level of analysis, there's nothing particular about HOT AMM vaults. The beauty of Arrakis Modular Public Vaults is that the specific complexities of a DEX (it's interfaces, LP decision space, and quirks) are abstracted away from depositors and every Arrakis Modular Public Vault has a simple UniswapV2-style experience, where LPs only make decisions about when and how much liquidity to provide, and when and how much liquidity to withdraw. The rest is a black box to an uncurious depositor who doesn't need to know how the liquidity is actively managed or even what DEX the liquidity is being supplied to. They can simple track the value and asset composition of their LP token at every block and decide if they are happy with the returns of the portfolio.

## Public Vault Owner

In Arrakis Modular, Public Vaults can only be created by whitelisted and thus trusted parties. The whitelisted vault creator initializes a new vault with it's _asset pair_, initial _module_, initial _management configuration_, and a _timelocked owner_ role who has sensitive powers to set and reset vault whitelisted _module(s)_ and vault _management configuration_. For every Public Vault created, a corresponding Timelock contract is also deployed which immutably controls ownership functions. The transferrable _owner_ role is set on this Timelock contract. Thus, a Public Vault owner has the power to adjust important and sensitive Vault parameters but these changes are **guaranteed to be behind (at least) a 48 hour timelock**.

This gives Public Vault depositors some time to react to vault parameter updates even in the worst case scenario (e.g. malicious Public Vault owner activity). In the future the whitelisted Public Vault creator role and timelocked Public Vault Owner role set on creation, would both be in the hands of the Arrakis DAO and controlled with onchain governance. As of today (15/10/2024) these roles are controlled by an Arrakis Multisig requiring 4 signatures.
