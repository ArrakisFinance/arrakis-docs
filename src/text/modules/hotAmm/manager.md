# Manager Functions

Note that ALL manager functions defined in Modules are subject to checks in the [ArrakisStandardManager](../../arrakisModular/technicalReference/metaVaults/core/contract.ArrakisStandardManager.md). Learn more about vault management and configurability [here](../../arrakisModular/architecture/configuration.md).

### Set Price Bounds

This module exposes a function where the manager can change the concentration of the Arrakis vault liquidity position.

```solidity
    function setPriceBounds(
        uint160 sqrtPriceLowX96_,
        uint160 sqrtPriceHighX96_,
        uint160 expectedSqrtSpotPriceUpperX96_,
        uint160 expectedSqrtSpotPriceLowerX96_
    ) external onlyManager {
```

### Swap

This module exposes a function where the manager can swap to rebalance Arrakis vault liquidity against another onchain liquidity source (atomically).

```solidity
    function swap(
        bool zeroForOne_,
        uint256 expectedMinReturn_,
        uint256 amountIn_,
        address router_,
        uint160 expectedSqrtSpotPriceUpperX96_,
        uint160 expectedSqrtSpotPriceLowerX96_,
        bytes calldata payload_
    ) external onlyManager whenNotPaused {
```

All modules also implement a `setManagerFeePIPS` and `withdrawManagerBalance` functions for handling Arrakis Protocol fee collection.

NOTE: while not executed through the `manager` role, the [Quoter](./quoter.md) functionality is another offchain process that HOT pools rely on.
