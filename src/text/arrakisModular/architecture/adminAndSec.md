# Admin and Security

Arrakis Modular employs a multi-layered security approach that combines proactive management, rapid response capabilities, and enforced delays on critical changes. The three core elements are the following:

1. **Arrakis Standard Manager**: serves as the entry point for active management of both private and public vaults. It implements additional safety checks to ensure delegated LP management is secure and trustless. It also handles the configuration and collection of management fees.
<p align="center">
<img src="../../../img/manager.svg" alt="nft" width="300" class="img-svg"/>
</p>

2. **Guardian**: responsible for implementing a _rushing pauser_ role that can quickly pause parts of the system in case of critical errors or vulnerabilities.

3. **TimeLock**: enforces a delay on changes to critical security parameters. This provides security guarantees for public Meta Vaults against compromised multisigs and malicious actors.
