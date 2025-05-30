# PancakeSwapV4StandardModuleResolver
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/modules/resolvers/PancakeSwapV4StandardModuleResolver.sol)

**Inherits:**
[IResolver](/autogenerated/interfaces/IResolver.sol/interface.IResolver.md), [IPancakeSwapV4StandardModuleResolver](/autogenerated/interfaces/IPancakeSwapV4StandardModuleResolver.sol/interface.IPancakeSwapV4StandardModuleResolver.md)


## State Variables
### poolManager

```solidity
address public immutable poolManager;
```


## Functions
### constructor


```solidity
constructor(
    address poolManager_
);
```

### getMintAmounts

getMintAmounts used to get the shares we can mint from some max amounts.


```solidity
function getMintAmounts(
    address vault_,
    uint256 maxAmount0_,
    uint256 maxAmount1_
)
    external
    view
    returns (
        uint256 shareToMint,
        uint256 amount0ToDeposit,
        uint256 amount1ToDeposit
    );
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`vault_`|`address`|meta vault address.|
|`maxAmount0_`|`uint256`|maximum amount of token0 user want to contribute.|
|`maxAmount1_`|`uint256`|maximum amount of token1 user want to contribute.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`shareToMint`|`uint256`|maximum amount of share user can get for 'maxAmount0_' and 'maxAmount1_'.|
|`amount0ToDeposit`|`uint256`|amount of token0 user should deposit into the vault for minting 'shareToMint'.|
|`amount1ToDeposit`|`uint256`|amount of token1 user should deposit into the vault for minting 'shareToMint'.|


### computeMintAmounts


```solidity
function computeMintAmounts(
    uint256 current0_,
    uint256 current1_,
    uint256 totalSupply_,
    uint256 amount0Max_,
    uint256 amount1Max_
) public pure returns (uint256 mintAmount);
```

