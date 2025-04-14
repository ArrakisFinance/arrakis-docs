# IVoter
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/arrakis-modular/blob/main/src/interfaces/IVoter.sol)


## Functions
### killGauge


```solidity
function killGauge(
    address _gauge
) external;
```

### gauges


```solidity
function gauges(
    address pool
) external view returns (address);
```

### isAlive


```solidity
function isAlive(
    address gauge
) external view returns (bool);
```

### emergencyCouncil


```solidity
function emergencyCouncil() external view returns (address);
```

