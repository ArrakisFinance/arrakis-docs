# PancakeSwapV4StandardModulePublic
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/modules/PancakeSwapV4StandardModulePublic.sol)

**Inherits:**
[PancakeSwapV4StandardModule](/src/abstracts/PancakeSwapV4StandardModule.sol/abstract.PancakeSwapV4StandardModule.md), [IArrakisLPModulePublic](/src/interfaces/IArrakisLPModulePublic.sol/interface.IArrakisLPModulePublic.md)

this module can only set pancake v4 pool that have generic hook,
that don't require specific action to become liquidity provider.


## State Variables
### id
*id = keccak256(abi.encode("PancakeSwapV4StandardModulePublic"))*


```solidity
bytes32 public constant id =
    0xf8a84b2e3e22d069766d4756d362bc5c6eb85d74765bf4feeb8c017f9e8c7937;
```


### notFirstDeposit

```solidity
bool public notFirstDeposit;
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
    whenNotPaused
    returns (uint256 amount0, uint256 amount1);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`depositor_`|`address`|address that will provide the tokens.|
|`proportion_`|`uint256`|proportion of position needed to be add.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 deposited.|
|`amount1`|`uint256`|amount of token1 deposited.|


### initializePosition


```solidity
function initializePosition(
    bytes calldata
) external override onlyMetaVault;
```

### withdraw

function used by metaVault to withdraw tokens from the strategy.


```solidity
function withdraw(
    address receiver_,
    uint256 proportion_
) public override returns (uint256 amount0, uint256 amount1);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`receiver_`|`address`|address that will receive tokens.|
|`proportion_`|`uint256`|proportion of position needed to be withdrawn.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 withdrawn.|
|`amount1`|`uint256`|amount of token1 withdrawn.|


### lockAcquired

Called by the pool manager on `msg.sender` when a lock is acquired


```solidity
function lockAcquired(
    bytes calldata data_
) public virtual returns (bytes memory);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`data_`|`bytes`|The data that was passed to the call to lock|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`bytes`|result data that you want to be returned from the lock call|


