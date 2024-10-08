# IPauser
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/interfaces/IPauser.sol)


## Functions
### pause


```solidity
function pause(address target_) external;
```

### whitelistPausers


```solidity
function whitelistPausers(address[] calldata pausers_) external;
```

### blacklistPausers


```solidity
function blacklistPausers(address[] calldata pausers_) external;
```

### isPauser


```solidity
function isPauser(address account) external view returns (bool);
```

## Events
### LogPauserWhitelisted

```solidity
event LogPauserWhitelisted(address[] indexed pauser);
```

### LogPauserBlacklisted

```solidity
event LogPauserBlacklisted(address[] indexed pauser);
```

### LogPause

```solidity
event LogPause(address indexed target);
```

## Errors
### AddressZero

```solidity
error AddressZero();
```

### AlreadyPauser

```solidity
error AlreadyPauser();
```

### NotPauser

```solidity
error NotPauser();
```

### OnlyPauser

```solidity
error OnlyPauser();
```

