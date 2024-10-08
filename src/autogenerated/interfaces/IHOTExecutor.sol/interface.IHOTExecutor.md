# IHOTExecutor
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/interfaces/IHOTExecutor.sol)


## Functions
### setW3f


```solidity
function setW3f(address newW3f_) external;
```

### rebalance


```solidity
function rebalance(
    address vault_,
    bytes[] calldata payloads_,
    uint256 expectedReservesAmount_,
    bool zeroToOne_
) external;
```

### manager


```solidity
function manager() external view returns (address);
```

### w3f


```solidity
function w3f() external view returns (address);
```

## Events
### LogSetW3f

```solidity
event LogSetW3f(address newW3f);
```

## Errors
### AddressZero

```solidity
error AddressZero();
```

### SameW3f

```solidity
error SameW3f();
```

### UnexpectedReservesAmount0

```solidity
error UnexpectedReservesAmount0();
```

### UnexpectedReservesAmount1

```solidity
error UnexpectedReservesAmount1();
```

### OnlyW3F

```solidity
error OnlyW3F();
```

