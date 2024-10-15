# Swap

For AMM swaps, the swap context should be left completely empty. The rest of the swap params can be set according to the user’s order.

Example AMM Swap Params

```solidity
    SovereignPoolSwapContextData memory data;
    SovereignPoolSwapParams memory params = SovereignPoolSwapParams({
        isSwapCallback: false,
        isZeroToOne: true,
        amountIn: 1e18,
        amountOutMin: 0,
        deadline: block.timestamp + 2,
        recipient: address(this),
        swapTokenOut: address(token1),
        swapContext: data
    });

    pool.swap(params);
```
