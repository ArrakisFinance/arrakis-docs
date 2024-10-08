# HOTExecutor
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/modules/HOTExecutor.sol)

**Inherits:**
[IHOTExecutor](/src/interfaces/IHOTExecutor.sol/interface.IHOTExecutor.md), Ownable


## State Variables
### manager

```solidity
address public immutable manager;
```


### w3f

```solidity
address public w3f;
```


## Functions
### constructor


```solidity
constructor(address manager_, address w3f_, address owner_);
```

### setW3f


```solidity
function setW3f(address newW3f_) external onlyOwner;
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

