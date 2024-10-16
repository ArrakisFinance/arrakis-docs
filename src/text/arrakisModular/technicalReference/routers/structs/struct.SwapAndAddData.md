# SwapAndAddData

[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/structs/SRouter.sol)

```solidity
struct SwapAndAddData {
    SwapData swapData;
    AddLiquidityData addData;
}
```

**Variables**

| Name       | Type                                               | Description                                                                  |
| ---------- | -------------------------------------------------- | ---------------------------------------------------------------------------- |
| `swapData` | [`SwapData`](./struct.SwapData.md)                 | SwapData struct containing data for swapping one of the tokens for the other |
| `addData`  | [`AddLiquidityData`](./struct.AddLiquidityData.md) | AddLiquidityData struct containing data for adding liquidity                 |
