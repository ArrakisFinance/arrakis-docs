# UniV4StandardModulePrivate
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/modules/UniV4StandardModulePrivate.sol)

**Inherits:**
[UniV4StandardModule](/src/abstracts/UniV4StandardModule.sol/abstract.UniV4StandardModule.md), [IArrakisLPModulePrivate](/src/interfaces/IArrakisLPModulePrivate.sol/interface.IArrakisLPModulePrivate.md)

this module can only set uni v4 pool that have generic hook,
that don't require specific action to become liquidity provider.


## Functions
### constructor


```solidity
constructor(
    address poolManager_,
    address guardian_
) UniV4StandardModule(poolManager_, guardian_);
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


### unlockCallback

Called by the pool manager on `msg.sender` when a lock is acquired


```solidity
function unlockCallback(bytes calldata data_)
    public
    virtual
    returns (bytes memory);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`data_`|`bytes`|The data that was passed to the call to lock|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`bytes`|result data that you want to be returned from the lock call|


### _fund

*use data to do specific action.*


```solidity
function _fund(
    IPoolManager poolManager_,
    address depositor_,
    uint256 amount0_,
    uint256 amount1_
) internal returns (bytes memory);
```

