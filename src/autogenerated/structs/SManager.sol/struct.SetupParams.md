# SetupParams
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/structs/SManager.sol)


```solidity
struct SetupParams {
    address vault;
    IOracleWrapper oracle;
    uint24 maxDeviation;
    uint256 cooldownPeriod;
    address executor;
    address stratAnnouncer;
    uint24 maxSlippagePIPS;
}
```

