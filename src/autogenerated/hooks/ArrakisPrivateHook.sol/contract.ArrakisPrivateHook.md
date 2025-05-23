# ArrakisPrivateHook
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/hooks/ArrakisPrivateHook.sol)

**Inherits:**
IHooks, [IArrakisPrivateHook](/autogenerated/interfaces/IArrakisPrivateHook.sol/interface.IArrakisPrivateHook.md)


## State Variables
### module

```solidity
address public immutable module;
```


### vault

```solidity
address public immutable vault;
```


### manager

```solidity
address public immutable manager;
```


### _zeroForOneFee

```solidity
uint24 internal _zeroForOneFee;
```


### _oneForZeroFee

```solidity
uint24 internal _oneForZeroFee;
```


## Functions
### constructor


```solidity
constructor(
    address module_
);
```

### setFees


```solidity
function setFees(
    uint24 zeroForOneFee_,
    uint24 oneForZeroFee_
) external;
```

### beforeInitialize

The hook called before the state of a pool is initialized.

*function not implemented, ArrakisPrivateHook will not support this hook.*


```solidity
function beforeInitialize(
    address,
    PoolKey calldata,
    uint160
) external virtual returns (bytes4);
```

### afterInitialize

The hook called after the state of a pool is initialized.

*function not implemented, ArrakisPrivateHook will not support this hook.*


```solidity
function afterInitialize(
    address,
    PoolKey calldata,
    uint160,
    int24
) external virtual returns (bytes4);
```

### beforeAddLiquidity

The hook called before liquidity is added


```solidity
function beforeAddLiquidity(
    address sender,
    PoolKey calldata,
    IPoolManager.ModifyLiquidityParams calldata,
    bytes calldata
) external virtual returns (bytes4);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`sender`|`address`|The initial msg.sender for the add liquidity call.|
|`<none>`|`PoolKey`||
|`<none>`|`IPoolManager.ModifyLiquidityParams`||
|`<none>`|`bytes`||


### afterAddLiquidity

The hook called after liquidity is added.

*function not implemented, ArrakisPrivateHook will not support this hook.*


```solidity
function afterAddLiquidity(
    address,
    PoolKey calldata,
    IPoolManager.ModifyLiquidityParams calldata,
    BalanceDelta,
    BalanceDelta,
    bytes calldata
) external virtual returns (bytes4, BalanceDelta);
```

### beforeRemoveLiquidity

The hook called before liquidity is removed.


```solidity
function beforeRemoveLiquidity(
    address,
    PoolKey calldata,
    IPoolManager.ModifyLiquidityParams calldata,
    bytes calldata
) external virtual returns (bytes4);
```

### afterRemoveLiquidity

The hook called after liquidity is removed.

*function not implemented, ArrakisPrivateHook will not support this hook.*


```solidity
function afterRemoveLiquidity(
    address,
    PoolKey calldata,
    IPoolManager.ModifyLiquidityParams calldata,
    BalanceDelta,
    BalanceDelta,
    bytes calldata
) external virtual returns (bytes4, BalanceDelta);
```

### beforeSwap

The hook called before a swap.


```solidity
function beforeSwap(
    address,
    PoolKey calldata,
    IPoolManager.SwapParams calldata swapParams_,
    bytes calldata
)
    external
    virtual
    returns (
        bytes4 funcSelector,
        BeforeSwapDelta,
        uint24 lpFeeOverride
    );
```

### afterSwap

The hook called after a swap.

*function not implemented, ArrakisPrivateHook will not support this hook.*


```solidity
function afterSwap(
    address,
    PoolKey calldata,
    IPoolManager.SwapParams calldata,
    BalanceDelta,
    bytes calldata
) external virtual returns (bytes4, int128);
```

### beforeDonate

The hook called before donate.

*function not implemented, ArrakisPrivateHook will not support this hook.*


```solidity
function beforeDonate(
    address,
    PoolKey calldata,
    uint256,
    uint256,
    bytes calldata
) external virtual returns (bytes4);
```

### afterDonate

The hook called after donate.

*function not implemented, ArrakisPrivateHook will not support this hook.*


```solidity
function afterDonate(
    address,
    PoolKey calldata,
    uint256,
    uint256,
    bytes calldata
) external virtual returns (bytes4);
```

### zeroForOneFee


```solidity
function zeroForOneFee() external view returns (uint24);
```

### oneForZeroFee


```solidity
function oneForZeroFee() external view returns (uint24);
```

### getHookPermissions


```solidity
function getHookPermissions()
    public
    pure
    virtual
    returns (Hooks.Permissions memory);
```

### _validateHookAddress


```solidity
function _validateHookAddress(
    IHooks _this
) internal pure virtual;
```

