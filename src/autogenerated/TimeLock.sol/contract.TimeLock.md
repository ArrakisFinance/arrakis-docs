# TimeLock
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/TimeLock.sol)

**Inherits:**
TimelockController, [ITimeLock](/src/interfaces/ITimeLock.sol/interface.ITimeLock.md)


## Functions
### constructor


```solidity
constructor(
    uint256 minDelay,
    address[] memory proposers,
    address[] memory executors,
    address admin
) TimelockController(minDelay, proposers, executors, admin);
```

### updateDelay

*override updateDelay function of TimelockController to not allow
update of delay.*


```solidity
function updateDelay(uint256) external pure override;
```

