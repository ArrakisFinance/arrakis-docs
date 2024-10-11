# Routers

Arrakis Routers serve as crucial intermediaries that enhance security, improve user experience, and optimize gas usage. By providing a standardized entry point, routers can implement additional safety checks, simplify complex multi-step processes into single transactions, and enable gas-efficient operations through batching. Some of the implementations are the following:

- **Public Meta Vault Router**: streamlines the process of adding liquidity to ArrakisMetaVaultPublic instances. It integrates Permit2, a standardized token approval system, which enhances both security and user experience.
- **Swap Executor**: is a sub-component of the Public Meta Vault Router. Its primary role is to execute token swaps in a secure manner. This middleman contract is necessary to mitigate potential security risks associated with low-level, generic swap operations.
