# Arrakis Modular Smart Contracts

Arrakis Modular represents the next evolution of the Arrakis onchain liquidity management protocol, aiming to overcome the limitations of previous versions (V1 and V2). Across versions, Arrakis vaults allow Liquidity Providers (LPs) to Decentralized Exchanges (DEXs) actively manage or delegate the management of their liquidity positions. However, Arrakis V1 and V2 were specifically built around Uniswap V3. Therefore, the previous standards were incompatible with other DEXs, and in order to support alternative venues (e.g. Uniswap V4, Balancer, Ambient, etc) Arrakis would have to make a completely new standard for every integration.

To address this, Arrakis Modular introduces a universal Meta-Vault standard. This modular framework enables the attachment of standardized modules to any two-sided liquidity provision protocol, simplifying the integration process. Key features include:
- **Flexibility**: Modules adhering to a common interface can be easily developed and attached, supporting a broad range of DEXs and use-cases.
- **Reusability**: The Arrakis Vault standard facilitates the reuse of components and maintenance of standard interfaces, streamlining future expansions.
- **Scalability**: Adapting to new liquidity pool types becomes straightforward, focusing on module development rather than protocol overhauls.

**With Arrakis Modular essentially any onchain DeFi strategy based on a dual-asset underlying can be created and tokenized, simply by developing the corresponding module which correctly adheres to the Arrakis Meta-Vault module interface**

We envision Arrakis Modular not only as a technical advancement internally, but as a platform for community and developer collaboration, inviting contributions to the ecosystem. With this modular approach, Arrakis Finance is poised to rapidly adapt to the evolving DeFi landscape, unlocking new possibilities for liquidity management.
 
Finally, note that the potential for modules extends beyond single DEX integrations. While current use cases focus on modules which each integrate an individual DEX liquidity provision protocol, in theory, modules could become more complex, enabling integrations with multiple DEXs simultaneously or combining DEX and peripheral protocols like lending markets or options protocols for advanced functionality (hedging and delta-neutral strategies etc). The architecture of Arrakis Modular supports such future innovations.

## System Design

At the heart of the Arrakis Modular system is the concept of Meta-Vaults. These Meta-Vaults enable users wishing to provide liquidity with two distinct assets to do so across any trading venue—without the need to deploy or migrate funds to new vaults. Meta-vaults, or from now on simply _vaults_, have the capability to whitelist various modules, essentially smart contracts that establish integration with liquidity-consuming dApps. This design ensures that as new DEXs emerge, liquidity provision becomes a matter of simply creating and whitelisting a new module compatible with the DEX, and then activating it.

Arrakis Modular strategically differentiates between Public Vaults and Private Vaults, offering tailored solutions for both ... 