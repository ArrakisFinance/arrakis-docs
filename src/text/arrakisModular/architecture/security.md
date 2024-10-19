# Security

Arrakis Modular employs a multi-layered security approach that combines proactive monitoring and rapid response capabilities with enforced delays on any critical changes.

1. **Guardian**: responsible for implementing a _rushing pauser_ role that can quickly pause parts of the system in case of critical errors or vulnerabilities.

2. **TimeLock**: enforces a delay on changes to critical security parameters. This provides security guarantees for public Meta Vaults against compromised multisigs and malicious actors.

### Upgradeability

Most of the Arrakis Modular smart contracts are entirely immutable. However _module implementations_ and the _ArrakisStandardManager_ are behind proxies and may be upgradeable as an initial safety precaution. **All upgradeability in Arrakis Modular is behind strict timelocks (controlled by Arrakis DAO) absolutely no instant contract upgrades can be made on the Arrakis Modular system**

(NOTE: the modular nature of Arrakis Meta Vaults make them inherently similar to upgradeable proxy patterns. By whitelisting and activating a new module, Arrakis Vault functionality can critically change. This is why Public Vault ownership enforces a timelock.)

### Audits

- [Audits Page](../../resources/audits.md)
