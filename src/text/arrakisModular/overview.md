# Arrakis Modular

Arrakis Modular represents the next evolution of the Arrakis liquidity management smart contract framework, aiming to overcome the limitations of previous versions (V1 and V2). 

Arrakis vault contracts have allowed LPs to actively manage or delegate the management of their DEX liquidity positions. However, Arrakis V1 and V2 were purpose-built around Uniswap V3 liquidity. To support alternative venues (e.g. Uniswap V4, Balancer, etc) Arrakis would have to make a completely new standard for each integration from scratch.

Arrakis Modular introduces a universal Meta Vault standard. This modular framework allows Arrakis to create entirely different two-sided LP Vault integrations, which all reuse the same Meta Vault infrastructure and interfaces. 
