# ModulePrivateRegistry
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/ModulePrivateRegistry.sol)

**Inherits:**
[ModuleRegistry](/src/abstracts/ModuleRegistry.sol/abstract.ModuleRegistry.md), [IModulePrivateRegistry](/src/interfaces/IModulePrivateRegistry.sol/interface.IModulePrivateRegistry.md)


## Functions
### constructor


```solidity
constructor(
    address owner_,
    address guardian_,
    address admin_
) ModuleRegistry(owner_, guardian_, admin_);
```

### createModule

function used to create module instance that can be
whitelisted as module inside a vault.


```solidity
function createModule(
    address vault_,
    address beacon_,
    bytes calldata payload_
) external returns (address module);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`vault_`|`address`||
|`beacon_`|`address`|which whitelisted beacon's implementation we want to create an instance of.|
|`payload_`|`bytes`|payload to create the module.|


