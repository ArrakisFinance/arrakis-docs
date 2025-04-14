# GetFeesPayload
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/arrakis-modular/blob/main/src/structs/SUniswapV3.sol)


```solidity
struct GetFeesPayload {
    uint256 feeGrowthInside0Last;
    uint256 feeGrowthInside1Last;
    IUniswapV3Pool pool;
    uint128 liquidity;
    int24 tick;
    int24 lowerTick;
    int24 upperTick;
}
```

