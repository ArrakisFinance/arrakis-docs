# IModulePublicRegistry
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/interfaces/IModulePublicRegistry.sol)


## Events
### LogCreatePublicModule
Log creation of a public module.


```solidity
event LogCreatePublicModule(
    address beacon,
    bytes payload,
    address vault,
    address creator,
    address module
);
```

**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`beacon`|`address`|which beacon from who we get the implementation.|
|`payload`|`bytes`|payload sent to the module constructor.|
|`vault`|`address`|address of the Arrakis Meta Vault that will own this module|
|`creator`|`address`|address that create the module.|
|`module`|`address`|address of the newly created module.|

## Errors
### NotPublicVault

```solidity
error NotPublicVault();
```

