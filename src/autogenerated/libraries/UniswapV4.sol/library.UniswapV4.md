# UniswapV4
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/arrakis-modular/blob/main/src/libraries/UniswapV4.sol)


## Functions
### rebalance


```solidity
function rebalance(
    IUniV4StandardModule self,
    PoolKey memory poolKey_,
    IUniV4StandardModule.LiquidityRange[] memory liquidityRanges_,
    SwapPayload memory swapPayload_,
    IUniV4StandardModule.Range[] storage ranges_,
    mapping(bytes32 => bool) storage activeRanges_
) public returns (bytes memory result);
```

### _collectAndSendFeesToManager

*here we are reasonning in term of token0 and token1 of vault (not poolKey).*


```solidity
function _collectAndSendFeesToManager(
    IPoolManager poolManager_,
    PoolKey memory poolKey_,
    address manager_,
    uint256 managerFeePIPS_,
    uint256 fee0_,
    uint256 fee1_
) internal returns (uint256 managerFee0, uint256 managerFee1);
```

### _modifyLiquidity


```solidity
function _modifyLiquidity(
    IPoolManager poolManager_,
    PoolKey memory poolKey_,
    IUniV4StandardModule.LiquidityRange[] memory liquidityRanges_,
    SwapPayload memory swapPayload_,
    IUniV4StandardModule.Range[] storage ranges_,
    mapping(bytes32 => bool) storage activeRanges_
) internal returns (RebalanceResult memory rebalanceResult);
```

### _rebalanceSettle

*principalDelta has negative values.*


```solidity
function _rebalanceSettle(
    IUniV4StandardModule self,
    PoolKey memory poolKey_,
    int256 amount0_,
    int256 amount1_
) internal;
```

### _collectFee


```solidity
function _collectFee(
    IPoolManager poolManager_,
    PoolKey memory poolKey_,
    mapping(bytes32 => bool) storage activeRanges_,
    int24 tickLower_,
    int24 tickUpper_
) internal returns (BalanceDelta feesAccrued);
```

### _addLiquidity


```solidity
function _addLiquidity(
    IPoolManager poolManager_,
    PoolKey memory poolKey_,
    IUniV4StandardModule.Range[] storage ranges_,
    mapping(bytes32 => bool) storage activeRanges_,
    uint128 liquidityToAdd_,
    int24 tickLower_,
    int24 tickUpper_
)
    internal
    returns (BalanceDelta callerDelta, BalanceDelta feesAccrued);
```

### _removeLiquidity


```solidity
function _removeLiquidity(
    IPoolManager poolManager_,
    PoolKey memory poolKey_,
    IUniV4StandardModule.Range[] storage ranges_,
    mapping(bytes32 => bool) storage activeRanges_,
    uint128 liquidityToRemove_,
    int24 tickLower_,
    int24 tickUpper_
)
    internal
    returns (BalanceDelta callerDelta, BalanceDelta feesAccrued);
```

### withdraw


```solidity
function withdraw(
    IUniV4StandardModule self,
    Withdraw memory withdraw_,
    IUniV4StandardModule.Range[] storage ranges_,
    mapping(bytes32 => bool) storage activeRanges_
) public returns (bytes memory result);
```

### _burnRanges

*if receiver is a smart contract, the sm should implement receive
fallback function.*

*if proportion is 100% we take all fees, to prevent
rounding errors.*


```solidity
function _burnRanges(
    PoolKey memory poolKey_,
    Withdraw memory withdraw_,
    IPoolManager poolManager_,
    IUniV4StandardModule.Range[] storage ranges_,
    mapping(bytes32 => bool) storage activeRanges_
) internal returns (BalanceDelta delta, BalanceDelta fees);
```

### _withdrawCollectExtraFees

*multiply -1 because we will remove liquidity.*


```solidity
function _withdrawCollectExtraFees(
    IPoolManager poolManager_,
    PoolKey memory poolKey_,
    uint256 amount0_,
    uint256 amount1_
) internal;
```

### deposit


```solidity
function deposit(
    IUniV4StandardModule self,
    Deposit memory deposit_,
    IUniV4StandardModule.Range[] storage ranges_
) public returns (bytes memory, bool);
```

### _checkMinReturn

*no need to rounding up because uni v4 should do it during minting.*

*no need to use Address lib for PoolManager.*

*currency1 cannot be native coin because address(0).*


```solidity
function _checkMinReturn(
    IUniV4StandardModule self,
    bool zeroForOne_,
    uint256 expectedMinReturn_,
    uint256 amountIn_,
    uint8 decimals0_,
    uint8 decimals1_
) internal view;
```

### _getRangeIndex


```solidity
function _getRangeIndex(
    IUniV4StandardModule.Range[] storage ranges_,
    int24 tickLower_,
    int24 tickUpper_
) internal view returns (uint256, uint256);
```

### _checkTokens


```solidity
function _checkTokens(
    PoolKey memory poolKey_,
    address token0_,
    address token1_,
    bool isInversed_
) internal pure;
```

### _checkPermissions

*Currency.unwrap(poolKey_.currency1) == address(0) is not possible*

*because currency0 should be lower currency1.*


```solidity
function _checkPermissions(
    PoolKey memory poolKey_
) internal;
```

### _getLeftOvers


```solidity
function _getLeftOvers(
    IUniV4StandardModule self,
    PoolKey memory poolKey_
) internal view returns (uint256 leftOver0, uint256 leftOver1);
```

### _getTokens


```solidity
function _getTokens(
    IUniV4StandardModule self,
    PoolKey memory poolKey_
) internal view returns (address _token0, address _token1);
```

### _getPoolRanges


```solidity
function _getPoolRanges(
    IUniV4StandardModule.Range[] storage ranges_,
    PoolKey memory poolKey_
) internal view returns (PoolRange[] memory poolRanges);
```

### _checkCurrencyBalances


```solidity
function _checkCurrencyBalances(
    IPoolManager poolManager_,
    PoolKey memory poolKey_
) internal view returns (uint256, uint256);
```

### _checkCurrencyDelta


```solidity
function _checkCurrencyDelta(
    int256 currency0BalanceRaw_,
    int256 currency1BalanceRaw_
) internal view returns (uint256, uint256);
```

