# PositionUnderlying
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/structs/SUniswapV4.sol)


```solidity
struct PositionUnderlying {
    uint160 sqrtPriceX96;
    IPoolManager poolManager;
    PoolKey poolKey;
    address self;
    int24 lowerTick;
    int24 upperTick;
}
```

