# GetFeesPayload
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/arrakis-modular/blob/main/src/structs/SUniswapV4.sol)


```solidity
struct GetFeesPayload {
    uint256 feeGrowthInside0Last;
    uint256 feeGrowthInside1Last;
    IPoolManager poolManager;
    PoolKey poolKey;
    uint128 liquidity;
    int24 tick;
    int24 lowerTick;
    int24 upperTick;
}
```

