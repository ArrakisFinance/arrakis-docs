# IPrivateRouterSwapExecutor
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/interfaces/IPrivateRouterSwapExecutor.sol)


## Functions
### swap

function used to swap tokens.


```solidity
function swap(SwapAndAddData memory _swapData)
    external
    payable
    returns (uint256 amount0Diff, uint256 amount1Diff);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`_swapData`|`SwapAndAddData`|struct containing all the informations for swapping.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0Diff`|`uint256`|the difference in token0 amount before and after the swap.|
|`amount1Diff`|`uint256`|the difference in token1 amount before and after the swap.|


## Errors
### OnlyRouter

```solidity
error OnlyRouter(address caller, address router);
```

### AddressZero

```solidity
error AddressZero();
```

### SwapCallFailed

```solidity
error SwapCallFailed();
```

### ReceivedBelowMinimum

```solidity
error ReceivedBelowMinimum();
```

