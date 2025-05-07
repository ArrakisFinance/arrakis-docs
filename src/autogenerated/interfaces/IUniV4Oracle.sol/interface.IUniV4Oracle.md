# IUniV4Oracle
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/interfaces/IUniV4Oracle.sol)


## Functions
### initialize


```solidity
function initialize(
    address module_
) external;
```

### module


```solidity
function module() external view returns (address);
```

### poolManager


```solidity
function poolManager() external view returns (address);
```

### decimals0


```solidity
function decimals0() external view returns (uint8);
```

### decimals1


```solidity
function decimals1() external view returns (uint8);
```

### isInversed


```solidity
function isInversed() external view returns (bool);
```

## Errors
### SqrtPriceZero

```solidity
error SqrtPriceZero();
```

