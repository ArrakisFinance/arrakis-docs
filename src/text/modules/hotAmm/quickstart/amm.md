# Permissionless AMM

In this section we describe the main actions that users can perform on the permissionless side of HOT AMM. We divide these actions into two sets:

- [Add Liquidty](addLiquidity.md) and [Remove Liquidity](removeLiquidity.md): For Liquidity Providers that want to fuel HOT AMM and earn from trading fees and incentives.
- [Swap](swap.md): For retail users and aggregators that desire to swap with low fees and up-to-date prices.

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
