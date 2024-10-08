# Overview

Arrakis Modular is the new improved version of Arrakis Finance’s LP vaults.

Our vaults have always had the goal of allowing LPs to configure or delegate active management of their DEX liquidity positions, and to expose shared liquidity provision strategies to passive participants who can simply hold an ERC20 “share” of the underlying LP strategy.

The goal is of Arrakis module was create a reusable Arrakis Vault standard, where most matching shared components can be reused and standard interfaces maintained, so that integrating a new type of Liquidity Pool in the future is reduced to just developing a new _module_ instead of an entirely new version of the Arrakis protocol.
