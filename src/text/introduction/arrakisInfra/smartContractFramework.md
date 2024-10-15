# Smart Contract Framework

Arrakis Modular represents the next evolution of the Arrakis onchain liquidity management protocol, aiming to overcome the limitations of previous versions (V1 and V2). To address this, Arrakis Modular introduces a universal Meta-Vault standard. This modular framework enables the attachment of standardized modules to any two-sided liquidity provision protocol, simplifying the integration process. Key features include:

- **Flexibility**: Modules adhering to a common interface can be easily developed and attached, supporting a broad range of DEXs and use-cases.
- **Reusability**: The Arrakis Vault standard facilitates the reuse of components and maintenance of standard interfaces, streamlining future expansions.
- **Scalability**: Adapting to new liquidity pool types becomes straightforward, focusing on module development rather than protocol overhauls.

Finally, note that the potential for modules extends beyond single DEX integrations. While current use cases focus on modules which each integrate an individual DEX liquidity provision protocol, in theory, modules could become more complex, enabling integrations with multiple DEXs simultaneously or combining DEX and peripheral protocols like lending markets or options protocols for advanced functionality (hedging and delta-neutral strategies etc). The architecture of Arrakis Modular supports such future innovations.

