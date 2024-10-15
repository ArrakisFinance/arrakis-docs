# IRouterSwapResolver

[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/interfaces/IRouterSwapResolver.sol)

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
