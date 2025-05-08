# ComputeFeesPayload
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/structs/SPancakeSwapV4.sol)


```solidity
struct ComputeFeesPayload {
    uint256 feeGrowthInsideLast;
    uint256 feeGrowthOutsideLower;
    uint256 feeGrowthOutsideUpper;
    uint256 feeGrowthGlobal;
    PoolId poolId;
    ICLPoolManager poolManager;
    uint128 liquidity;
    int24 tick;
    int24 lowerTick;
    int24 upperTick;
}
```

