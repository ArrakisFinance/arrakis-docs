# SwapPayload
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/structs/SUniswapV3.sol)


```solidity
struct SwapPayload {
    bytes payload;
    address router;
    uint256 amountIn;
    uint256 expectedMinReturn;
    bool zeroForOne;
}
```

