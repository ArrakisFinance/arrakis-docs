# PositionUnderlying
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/structs/SPancakeSwapV4.sol)


```solidity
struct PositionUnderlying {
    uint160 sqrtPriceX96;
    ICLPoolManager poolManager;
    PoolKey poolKey;
    address self;
    int24 tick;
    int24 lowerTick;
    int24 upperTick;
}
```

