# IUniV4StandardModule
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/interfaces/IUniV4StandardModule.sol)


## Functions
### initialize


```solidity
function initialize(
    uint256 init0_,
    uint256 init1_,
    bool isInversed_,
    PoolKey calldata poolKey_,
    IOracleWrapper oracle_,
    uint24 maxSlippage_,
    address metaVault_
) external;
```

### setPool


```solidity
function setPool(
    PoolKey calldata poolKey_,
    LiquidityRange[] calldata liquidityRanges_,
    SwapPayload calldata swapPayload_
) external;
```

### rebalance


```solidity
function rebalance(
    LiquidityRange[] calldata liquidityRanges_,
    SwapPayload memory swapPayload_
)
    external
    returns (
        uint256 amount0Minted,
        uint256 amount1Minted,
        uint256 amount0Burned,
        uint256 amount1Burned
    );
```

### getRanges

function used to get the list of active ranges.


```solidity
function getRanges() external view returns (Range[] memory ranges);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`ranges`|`Range[]`|active ranges|


### poolKey


```solidity
function poolKey()
    external
    view
    returns (
        Currency currency0,
        Currency currency1,
        uint24 fee,
        int24 tickSpacing,
        IHooks hooks
    );
```

## Events
### LogSetPool

```solidity
event LogSetPool(PoolKey oldPoolKey, PoolKey poolKey);
```

### LogRebalance

```solidity
event LogRebalance(
    LiquidityRange[] liquidityRanges,
    uint256 amount0Minted,
    uint256 amount1Minted,
    uint256 amount0Burned,
    uint256 amount1Burned
);
```

## Errors
### Currency0DtToken0

```solidity
error Currency0DtToken0(address currency0, address token0);
```

### Currency1DtToken1

```solidity
error Currency1DtToken1(address currency1, address token1);
```

### Currency1DtToken0

```solidity
error Currency1DtToken0(address currency1, address token0);
```

### Currency0DtToken1

```solidity
error Currency0DtToken1(address currency0, address token1);
```

### SqrtPriceZero

```solidity
error SqrtPriceZero();
```

### OnlyPoolManager

```solidity
error OnlyPoolManager();
```

### OnlyModuleCaller

```solidity
error OnlyModuleCaller();
```

### InvalidCurrencyDelta

```solidity
error InvalidCurrencyDelta();
```

### RangeShouldBeActive

```solidity
error RangeShouldBeActive(int24 tickLower, int24 tickUpper);
```

### OverBurning

```solidity
error OverBurning();
```

### TicksMisordered

```solidity
error TicksMisordered(int24 tickLower, int24 tickUpper);
```

### TickLowerOutOfBounds

```solidity
error TickLowerOutOfBounds(int24 tickLower);
```

### TickUpperOutOfBounds

```solidity
error TickUpperOutOfBounds(int24 tickUpper);
```

### OnlyMetaVaultOrManager

```solidity
error OnlyMetaVaultOrManager();
```

### SamePool

```solidity
error SamePool();
```

### NoRemoveLiquidityHooks

```solidity
error NoRemoveLiquidityHooks();
```

### OverMaxDeviation

```solidity
error OverMaxDeviation();
```

### CallBackNotSupported

```solidity
error CallBackNotSupported();
```

### NativeCoinCannotBeToken1

```solidity
error NativeCoinCannotBeToken1();
```

### MaxSlippageGtTenPercent

```solidity
error MaxSlippageGtTenPercent();
```

### ExpectedMinReturnTooLow

```solidity
error ExpectedMinReturnTooLow();
```

### WrongRouter

```solidity
error WrongRouter();
```

### SlippageTooHigh

```solidity
error SlippageTooHigh();
```

## Structs
### Range

```solidity
struct Range {
    int24 tickLower;
    int24 tickUpper;
}
```

### LiquidityRange

```solidity
struct LiquidityRange {
    Range range;
    int128 liquidity;
}
```

