# Pauser
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/Pauser.sol)

**Inherits:**
[IPauser](/src/interfaces/IPauser.sol/interface.IPauser.md), Ownable


## State Variables
### _pausers

```solidity
EnumerableSet.AddressSet internal _pausers;
```


## Functions
### constructor


```solidity
constructor(address pauser_, address owner_);
```

### pause


```solidity
function pause(address target_) external override;
```

### whitelistPausers


```solidity
function whitelistPausers(address[] calldata pausers_)
    external
    override
    onlyOwner;
```

### blacklistPausers


```solidity
function blacklistPausers(address[] calldata pausers_)
    external
    override
    onlyOwner;
```

### isPauser


```solidity
function isPauser(address account_) public view returns (bool);
```

