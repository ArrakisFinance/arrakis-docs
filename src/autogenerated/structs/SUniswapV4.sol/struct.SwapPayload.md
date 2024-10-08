# SwapPayload
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/structs/SUniswapV4.sol)


```solidity
struct SwapPayload {
    bytes payload;
    address router;
    uint256 amountIn;
    uint256 expectedMinReturn;
    bool zeroForOne;
}
```

