# HOTOracleWrapper
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/modules/HOTOracleWrapper.sol)

**Inherits:**
[IOracleWrapper](/src/interfaces/IOracleWrapper.sol/interface.IOracleWrapper.md)


## State Variables
### oracle

```solidity
IHOTOracle public immutable oracle;
```


### decimals0

```solidity
uint8 public immutable decimals0;
```


### decimals1

```solidity
uint8 public immutable decimals1;
```


## Functions
### constructor


```solidity
constructor(address oracle_, uint8 decimals0_, uint8 decimals1_);
```

### getPrice0


```solidity
function getPrice0() public view returns (uint256 price0);
```

### getPrice1


```solidity
function getPrice1() public view returns (uint256 price1);
```

