# GetFeesPayload
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/structs/SPancakeSwapV4.sol)


```solidity
struct GetFeesPayload {
    uint256 feeGrowthInside0Last;
    uint256 feeGrowthInside1Last;
    PoolId poolId;
    ICLPoolManager poolManager;
    uint128 liquidity;
    int24 tick;
    int24 lowerTick;
    int24 upperTick;
}
```

