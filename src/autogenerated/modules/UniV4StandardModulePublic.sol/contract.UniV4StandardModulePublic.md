# UniV4StandardModulePublic
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/modules/UniV4StandardModulePublic.sol)

**Inherits:**
[UniV4StandardModule](/src/abstracts/UniV4StandardModule.sol/abstract.UniV4StandardModule.md), [IArrakisLPModulePublic](/src/interfaces/IArrakisLPModulePublic.sol/interface.IArrakisLPModulePublic.md)

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

### deposit

function used by metaVault to deposit tokens into the strategy.


```solidity
function deposit(
    address depositor_,
    uint256 proportion_
)
    external
    payable
    onlyMetaVault
    nonReentrant
    returns (uint256 amount0, uint256 amount1);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`depositor_`|`address`|address that will provide the tokens.|
|`proportion_`|`uint256`|number of share needed to be add.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 deposited.|
|`amount1`|`uint256`|amount of token1 deposited.|


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


### _deposit

*use data to do specific action.*


```solidity
function _deposit(
    IPoolManager poolManager_,
    address depositor_,
    uint256 proportion_
) internal returns (bytes memory);
```

