# IPancakeSwapV4StandardModuleResolver
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/interfaces/IPancakeSwapV4StandardModuleResolver.sol)


## Functions
### poolManager


```solidity
function poolManager() external returns (address);
```

### computeMintAmounts


```solidity
function computeMintAmounts(
    uint256 current0_,
    uint256 current1_,
    uint256 totalSupply_,
    uint256 amount0Max_,
    uint256 amount1Max_
) external pure returns (uint256 mintAmount);
```

## Errors
### MaxAmountsTooLow

```solidity
error MaxAmountsTooLow();
```

### AddressZero

```solidity
error AddressZero();
```

### MintZero

```solidity
error MintZero();
```

### NotSupported

```solidity
error NotSupported();
```

