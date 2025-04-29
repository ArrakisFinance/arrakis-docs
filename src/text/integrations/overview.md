# Integrations

One key feature of Arrakis Modular is the ability to switch between **modules**, where each module defines the vault's integration with a liquidity consuming dApp. For Arrakis Pro there are currently four potential **modules**:

1. [Uniswap v4](./uniswapv4.md):

2. [Aerodrome](./aerodrome.md):

2. [Velodrome](./aerodrome.md):

2. [Pancakeswap v4](./pancakeswapv4.md): Coming soon...

## How to whitelist a new module

From `vault.owner()` acct -> call [whitelistModules](../../../text/arrakisModular/technicalReference/metaVaults/core/abstract.ArrakisMetaVault.html#whitelistmodules) on your vault contract. Since the correct input params could be complex you may want to consult Arrakis engineers.

## More on Arrakis Modular

The potential for integrations extends beyond single DEXs. While current use cases focus on modules which each integrate an individual DEX liquidity provision protocol, in theory, modules could become more complex, enabling integrations with multiple DEXs simultaneously or combining DEX and peripheral protocols like lending markets or options protocols for advanced functionality (hedging and delta-neutral strategies etc). The architecture of Arrakis Modular supports such future innovations.