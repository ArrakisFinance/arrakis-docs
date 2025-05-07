# PancakeSwapV4StandardModulePrivate
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/a0f994c9f79e57468b66cd97f5a9ed37ecef770d/src/modules/PancakeSwapV4StandardModulePrivate.sol)

**Inherits:**
[PancakeSwapV4StandardModule](/src/abstracts/PancakeSwapV4StandardModule.sol/abstract.PancakeSwapV4StandardModule.md), [IArrakisLPModulePrivate](/src/interfaces/IArrakisLPModulePrivate.sol/interface.IArrakisLPModulePrivate.md)


## State Variables
### id
*id = keccak256(abi.encode("PancakeSwapV4StandardModulePrivate"))*


```solidity
bytes32 public constant id =
    0x7cec99d521e59378e389a879513f6373dd58e86a0c1422fa01195032b7071950;
```


## Functions
### constructor


```solidity
constructor(
    address poolManager_,
    address guardian_,
    address vault_,
    address distributor_,
    address collector_
)
    PancakeSwapV4StandardModule(
        poolManager_,
        guardian_,
        vault_,
        distributor_,
        collector_
    );
```

### fund

fund function for private vault.


```solidity
function fund(
    address depositor_,
    uint256 amount0_,
    uint256 amount1_
) external payable onlyMetaVault whenNotPaused nonReentrant;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`depositor_`|`address`|address that will provide the tokens.|
|`amount0_`|`uint256`|amount of token0 that depositor want to send to module.|
|`amount1_`|`uint256`|amount of token1 that depositor want to send to module.|


### _fund


```solidity
function _fund(
    address depositor_,
    uint256 amount0_,
    uint256 amount1_
) internal;
```

### lockAcquired


```solidity
function lockAcquired(
    bytes calldata data_
) public virtual returns (bytes memory);
```

