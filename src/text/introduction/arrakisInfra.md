# Arrakis Protocol

Arrakis Protocol consists of two major infrastructural components:

- Offchain Market Making Infrastructure
- Onchain Smart Contract Framework

Our Offchain Market Making Infrastructure together with our Onchain Smart Contract Framework for DEX integrations comprise the Arrakis Protocol.

<p align="center">
<img src="../../../img/arrakis-infra-overview.svg" alt="arrakis-modular" width="500" class="img-svg"/>
</p>

For example, the new [HOT AMM Public Vault](../arrakisModular/publicVaults.md) is formed by the following components:

- Arrakis Quoter and other offchain market making components.
- Arrakis Modular (smart contract framework) using public vaults.
- A new custom Valantis Sovereign Pool (as the 1st DEX integration).