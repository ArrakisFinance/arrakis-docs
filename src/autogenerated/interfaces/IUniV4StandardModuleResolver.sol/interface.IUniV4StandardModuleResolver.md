# IUniV4StandardModuleResolver
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/interfaces/IUniV4StandardModuleResolver.sol)


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

