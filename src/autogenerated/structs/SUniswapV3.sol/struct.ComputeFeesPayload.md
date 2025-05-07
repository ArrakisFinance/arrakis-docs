# ComputeFeesPayload
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/structs/SUniswapV3.sol)


```solidity
struct ComputeFeesPayload {
    uint256 feeGrowthInsideLast;
    uint256 feeGrowthOutsideLower;
    uint256 feeGrowthOutsideUpper;
    uint256 feeGrowthGlobal;
    uint128 liquidity;
    int24 tick;
    int24 lowerTick;
    int24 upperTick;
}
```

