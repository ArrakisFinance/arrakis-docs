# IBunkerModule
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/interfaces/IBunkerModule.sol)


## Functions
### initialize

initialize function to delegate call onced the beacon proxy is deployed,
for initializing the bunker module.


```solidity
function initialize(address metaVault_) external;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`metaVault_`|`address`|address of the meta vault|


## Errors
### NotImplemented

```solidity
error NotImplemented();
```

### AmountsZeros

```solidity
error AmountsZeros();
```

