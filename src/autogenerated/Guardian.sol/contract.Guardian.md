# Guardian
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/Guardian.sol)

**Inherits:**
Ownable, [IGuardian](/src/interfaces/IGuardian.sol/interface.IGuardian.md)


## State Variables
### pauser

```solidity
address public pauser;
```


## Functions
### constructor


```solidity
constructor(address owner_, address pauser_);
```

### setPauser

function to set the pauser of Arrakis protocol.


```solidity
function setPauser(address newPauser_) external onlyOwner;
```
