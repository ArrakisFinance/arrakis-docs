# Arrakis Modular

Arrakis Modular represents the next evolution of the Arrakis onchain liquidity management protocol, aiming to overcome the limitations of previous versions (V1 and V2). 

Across versions, Arrakis vaults allow Liquidity Providers (LPs) to Decentralized Exchanges (DEXs) actively manage or delegate the management of their liquidity positions. However, Arrakis V1 and V2 were purpose-built around Uniswap V3. Therefore, the previous standards were incompatible with other DEXs, and in order to support alternative venues (e.g. Uniswap V4, Balancer, Ambient, etc) Arrakis would have to make a completely new standard for every integration.

To address this, Arrakis Modular introduces a universal Meta Vault standard. This modular framework enables the attachment of standardized modules to any two-sided liquidity provision protocol, simplifying the integration process. Key features include:

- _Flexibility_: Modules adhering to a common interface can be easily developed and attached, supporting a broad range of DEXs and use-cases.
- _Reusability_: The Arrakis Vault standard facilitates the reuse of components and maintenance of standard interfaces, streamlining future expansions.
- _Scalability_: Adapting to new liquidity pool types becomes straightforward, focusing on module development rather than protocol overhauls.

**With Arrakis Modular essentially any onchain DeFi strategy based on a dual-asset underlying can be created and tokenized, simply by developing the corresponding module which correctly adheres to the Arrakis Meta Vault module interface**
