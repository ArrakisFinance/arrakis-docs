# IRouterSwapResolver
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/interfaces/IRouterSwapResolver.sol)


## Functions
### calculateSwapAmount


```solidity
function calculateSwapAmount(
    IArrakisMetaVault vault,
    uint256 amount0In,
    uint256 amount1In,
    uint256 price18Decimals
) external view returns (bool zeroForOne, uint256 swapAmount);
```

## Errors
### AddressZero

```solidity
error AddressZero();
```

