# ArrakisPublicVaultRouterV2
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/ArrakisPublicVaultRouterV2.sol)

**Inherits:**
[IArrakisPublicVaultRouterV2](/src/interfaces/IArrakisPublicVaultRouterV2.sol/interface.IArrakisPublicVaultRouterV2.md), ReentrancyGuard, Ownable, Pausable


## State Variables
### nativeToken

```solidity
address public immutable nativeToken;
```


### permit2

```solidity
IPermit2 public immutable permit2;
```


### factory

```solidity
IArrakisMetaVaultFactory public immutable factory;
```


### weth

```solidity
IWETH9 public immutable weth;
```


### swapper

```solidity
IRouterSwapExecutor public swapper;
```


### _resolvers

```solidity
EnumerableSet.AddressSet internal _resolvers;
```


## Functions
### onlyPublicVault


```solidity
modifier onlyPublicVault(address vault_);
```

### constructor


```solidity
constructor(
    address nativeToken_,
    address permit2_,
    address owner_,
    address factory_,
    address weth_
);
```

### pause

function used to pause the router.

*only callable by owner*


```solidity
function pause() external onlyOwner;
```

### unpause

function used to unpause the router.

*only callable by owner*


```solidity
function unpause() external onlyOwner;
```

### updateSwapExecutor


```solidity
function updateSwapExecutor(address swapper_)
    external
    whenNotPaused
    onlyOwner;
```

### whitelistResolvers


```solidity
function whitelistResolvers(address[] calldata resolvers_)
    external
    whenNotPaused
    onlyOwner;
```

### blacklistResolvers


```solidity
function blacklistResolvers(address[] calldata resolvers_)
    external
    whenNotPaused
    onlyOwner;
```

### addLiquidity

addLiquidity adds liquidity to meta vault of interest (mints L tokens)


```solidity
function addLiquidity(
    AddLiquidityData memory params_,
    address resolver_
)
    external
    payable
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.vault)
    returns (uint256 amount0, uint256 amount1, uint256 sharesReceived);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`AddLiquidityData`|AddLiquidityData struct containing data for adding liquidity|
|`resolver_`|`address`|Address of resolver contract that will compute mint amount.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 transferred from msg.sender to mint `mintAmount`|
|`amount1`|`uint256`|amount of token1 transferred from msg.sender to mint `mintAmount`|
|`sharesReceived`|`uint256`|amount of public vault tokens transferred to `receiver`|


### swapAndAddLiquidity

swapAndAddLiquidity transfer tokens to and calls RouterSwapExecutor


```solidity
function swapAndAddLiquidity(
    SwapAndAddData memory params_,
    address resolver_
)
    external
    payable
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.addData.vault)
    returns (
        uint256 amount0,
        uint256 amount1,
        uint256 sharesReceived,
        uint256 amount0Diff,
        uint256 amount1Diff
    );
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`SwapAndAddData`|SwapAndAddData struct containing data for swap|
|`resolver_`|`address`|address of the contract that will compute mint amounts.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 transferred from msg.sender to mint `mintAmount`|
|`amount1`|`uint256`|amount of token1 transferred from msg.sender to mint `mintAmount`|
|`sharesReceived`|`uint256`|amount of public vault tokens transferred to `receiver`|
|`amount0Diff`|`uint256`|token0 balance difference post swap|
|`amount1Diff`|`uint256`|token1 balance difference post swap|


### removeLiquidity

removeLiquidity removes liquidity from vault and burns LP tokens


```solidity
function removeLiquidity(RemoveLiquidityData memory params_)
    external
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.vault)
    returns (uint256 amount0, uint256 amount1);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`RemoveLiquidityData`|RemoveLiquidityData struct containing data for withdrawals|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|actual amount of token0 transferred to receiver for burning `burnAmount`|
|`amount1`|`uint256`|actual amount of token1 transferred to receiver for burning `burnAmount`|


### addLiquidityPermit2

addLiquidityPermit2 adds liquidity to public vault of interest (mints LP tokens)


```solidity
function addLiquidityPermit2(
    AddLiquidityPermit2Data memory params_,
    address resolver_
)
    external
    payable
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.addData.vault)
    returns (uint256 amount0, uint256 amount1, uint256 sharesReceived);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`AddLiquidityPermit2Data`|AddLiquidityPermit2Data struct containing data for adding liquidity|
|`resolver_`|`address`|Address of the resolver contract that will compute the mint amounts.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 transferred from msg.sender to mint `mintAmount`|
|`amount1`|`uint256`|amount of token1 transferred from msg.sender to mint `mintAmount`|
|`sharesReceived`|`uint256`|amount of public vault tokens transferred to `receiver`|


### swapAndAddLiquidityPermit2

swapAndAddLiquidityPermit2 transfer tokens to and calls RouterSwapExecutor


```solidity
function swapAndAddLiquidityPermit2(
    SwapAndAddPermit2Data memory params_,
    address resolver_
)
    external
    payable
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.swapAndAddData.addData.vault)
    returns (
        uint256 amount0,
        uint256 amount1,
        uint256 sharesReceived,
        uint256 amount0Diff,
        uint256 amount1Diff
    );
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`SwapAndAddPermit2Data`|SwapAndAddPermit2Data struct containing data for swap|
|`resolver_`|`address`|Address of the contract that will|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 transferred from msg.sender to mint `mintAmount`|
|`amount1`|`uint256`|amount of token1 transferred from msg.sender to mint `mintAmount`|
|`sharesReceived`|`uint256`|amount of public vault tokens transferred to `receiver`|
|`amount0Diff`|`uint256`|token0 balance difference post swap|
|`amount1Diff`|`uint256`|token1 balance difference post swap|


### removeLiquidityPermit2

removeLiquidityPermit2 removes liquidity from vault and burns LP tokens


```solidity
function removeLiquidityPermit2(
    RemoveLiquidityPermit2Data memory params_
)
    external
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.removeData.vault)
    returns (uint256 amount0, uint256 amount1);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`RemoveLiquidityPermit2Data`|RemoveLiquidityPermit2Data struct containing data for withdrawals|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|actual amount of token0 transferred to receiver for burning `burnAmount`|
|`amount1`|`uint256`|actual amount of token1 transferred to receiver for burning `burnAmount`|


### wrapAndAddLiquidity

wrapAndAddLiquidity wrap eth and adds liquidity to meta vault of interest (mints L tokens)


```solidity
function wrapAndAddLiquidity(
    AddLiquidityData memory params_,
    address resolver_
)
    external
    payable
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.vault)
    returns (uint256 amount0, uint256 amount1, uint256 sharesReceived);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`AddLiquidityData`|AddLiquidityData struct containing data for adding liquidity|
|`resolver_`|`address`|Address of the resolver contract that will compute mint amounts.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 transferred from msg.sender to mint `mintAmount`|
|`amount1`|`uint256`|amount of token1 transferred from msg.sender to mint `mintAmount`|
|`sharesReceived`|`uint256`|amount of public vault tokens transferred to `receiver`|


### wrapAndSwapAndAddLiquidity

wrapAndSwapAndAddLiquidity wrap eth and transfer tokens to and calls RouterSwapExecutor


```solidity
function wrapAndSwapAndAddLiquidity(
    SwapAndAddData memory params_,
    address resolver_
)
    external
    payable
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.addData.vault)
    returns (
        uint256 amount0,
        uint256 amount1,
        uint256 sharesReceived,
        uint256 amount0Diff,
        uint256 amount1Diff
    );
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`SwapAndAddData`|SwapAndAddData struct containing data for swap|
|`resolver_`|`address`|Address of the resolver contract that will compute mint amounts.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 transferred from msg.sender to mint `mintAmount`|
|`amount1`|`uint256`|amount of token1 transferred from msg.sender to mint `mintAmount`|
|`sharesReceived`|`uint256`|amount of public vault tokens transferred to `receiver`|
|`amount0Diff`|`uint256`|token0 balance difference post swap|
|`amount1Diff`|`uint256`|token1 balance difference post swap|


### wrapAndAddLiquidityPermit2

wrapAndAddLiquidityPermit2 wrap eth and adds liquidity to public vault of interest (mints LP tokens)

*hack to get rid of stack too depth*


```solidity
function wrapAndAddLiquidityPermit2(
    AddLiquidityPermit2Data memory params_,
    address resolver_
)
    external
    payable
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.addData.vault)
    returns (uint256 amount0, uint256 amount1, uint256 sharesReceived);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`AddLiquidityPermit2Data`|AddLiquidityPermit2Data struct containing data for adding liquidity|
|`resolver_`|`address`|Address of the contract that will compute mint amounts.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 transferred from msg.sender to mint `mintAmount`|
|`amount1`|`uint256`|amount of token1 transferred from msg.sender to mint `mintAmount`|
|`sharesReceived`|`uint256`|amount of public vault tokens transferred to `receiver`|


### wrapAndSwapAndAddLiquidityPermit2

wrapAndSwapAndAddLiquidityPermit2 wrap eth and transfer tokens to and calls RouterSwapExecutor


```solidity
function wrapAndSwapAndAddLiquidityPermit2(
    SwapAndAddPermit2Data memory params_,
    address resolver_
)
    external
    payable
    nonReentrant
    whenNotPaused
    onlyPublicVault(params_.swapAndAddData.addData.vault)
    returns (
        uint256 amount0,
        uint256 amount1,
        uint256 sharesReceived,
        uint256 amount0Diff,
        uint256 amount1Diff
    );
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`params_`|`SwapAndAddPermit2Data`|SwapAndAddPermit2Data struct containing data for swap|
|`resolver_`|`address`|address that will compute mint amounts.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 transferred from msg.sender to mint `mintAmount`|
|`amount1`|`uint256`|amount of token1 transferred from msg.sender to mint `mintAmount`|
|`sharesReceived`|`uint256`|amount of public vault tokens transferred to `receiver`|
|`amount0Diff`|`uint256`|token0 balance difference post swap|
|`amount1Diff`|`uint256`|token1 balance difference post swap|


### receive

*hack to get rid of stack too depth*


```solidity
receive() external payable;
```

### getMintAmounts

getMintAmounts used to get the shares we can mint from some max amounts.


```solidity
function getMintAmounts(
    address vault_,
    uint256 maxAmount0_,
    uint256 maxAmount1_,
    address resolver_
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
|`resolver_`|`address`|address of the contract that will compute mint amount.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`shareToMint`|`uint256`|maximum amount of share user can get for 'maxAmount0_' and 'maxAmount1_'.|
|`amount0ToDeposit`|`uint256`|amount of token0 user should deposit into the vault for minting 'shareToMint'.|
|`amount1ToDeposit`|`uint256`|amount of token1 user should deposit into the vault for minting 'shareToMint'.|


### resolvers


```solidity
function resolvers() external view returns (address[] memory);
```

### _addLiquidity


```solidity
function _addLiquidity(
    address vault_,
    uint256 amount0_,
    uint256 amount1_,
    uint256 shares_,
    address receiver_,
    address token0_,
    address token1_
) internal;
```

### _swapAndAddLiquidity


```solidity
function _swapAndAddLiquidity(
    SwapAndAddData memory params_,
    address token0_,
    address token1_,
    address resolver_
)
    internal
    returns (
        uint256 amount0Use,
        uint256 amount1Use,
        uint256 amount0,
        uint256 amount1,
        uint256 sharesReceived,
        uint256 amount0Diff,
        uint256 amount1Diff
    );
```

### _swapAndAddLiquiditySendBackLeftOver


```solidity
function _swapAndAddLiquiditySendBackLeftOver(
    SwapAndAddData memory params_,
    address token0_,
    address token1_,
    address resolver_
)
    internal
    returns (
        uint256 amount0,
        uint256 amount1,
        uint256 sharesReceived,
        uint256 amount0Diff,
        uint256 amount1Diff
    );
```

### _removeLiquidity


```solidity
function _removeLiquidity(RemoveLiquidityData memory params_)
    internal
    returns (uint256 amount0, uint256 amount1);
```

### _permit2AddLengthOne


```solidity
function _permit2AddLengthOne(
    AddLiquidityPermit2Data memory params_,
    address token0_,
    address token1_,
    uint256 amount0_,
    uint256 amount1_
) internal;
```

### _permit2AddLengthOneOrTwo


```solidity
function _permit2AddLengthOneOrTwo(
    AddLiquidityPermit2Data memory params_,
    address token0_,
    address token1_,
    uint256 amount0_,
    uint256 amount1_
) internal;
```

### _permit2Add


```solidity
function _permit2Add(
    uint256 permittedLength_,
    AddLiquidityPermit2Data memory params_,
    address token0_,
    address token1_,
    uint256 amount0_,
    uint256 amount1_
) internal;
```

### _permit2SwapAndAddLengthOne


```solidity
function _permit2SwapAndAddLengthOne(
    SwapAndAddPermit2Data memory params_,
    address token0_,
    address token1_
) internal;
```

### _permit2SwapAndAddLengthOneOrTwo


```solidity
function _permit2SwapAndAddLengthOneOrTwo(
    SwapAndAddPermit2Data memory params_,
    address token0_,
    address token1_
) internal;
```

### _permit2SwapAndAdd


```solidity
function _permit2SwapAndAdd(
    uint256 permittedLength_,
    SwapAndAddPermit2Data memory params_,
    address token0_,
    address token1_
) internal;
```

### _getMintAmounts


```solidity
function _getMintAmounts(
    address vault_,
    uint256 maxAmount0_,
    uint256 maxAmount1_,
    address resolver_
)
    internal
    view
    returns (
        uint256 shareToMint,
        uint256 amount0ToDeposit,
        uint256 amount1ToDeposit
    );
```

