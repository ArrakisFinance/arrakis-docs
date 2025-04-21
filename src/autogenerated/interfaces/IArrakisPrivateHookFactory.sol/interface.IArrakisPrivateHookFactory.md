# IArrakisPrivateHookFactory
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/interfaces/IArrakisPrivateHookFactory.sol)


## Functions
### createPrivateHook


```solidity
function createPrivateHook(
    address module_,
    bytes32 salt_
) external returns (address hook);
```

### addressOf


```solidity
function addressOf(
    bytes32 salt_
) external view returns (address);
```

## Errors
### AddressZero

```solidity
error AddressZero();
```

