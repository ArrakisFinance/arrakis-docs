# RebalanceParams
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/structs/SUniswapV3.sol)


```solidity
struct RebalanceParams {
    ModifyPosition[] decreasePositions;
    ModifyPosition[] increasePositions;
    SwapPayload swapPayload;
    INonfungiblePositionManager.MintParams[] mintParams;
    uint256 minBurn0;
    uint256 minBurn1;
    uint256 minDeposit0;
    uint256 minDeposit1;
}
```

