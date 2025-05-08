# PancakeSwapV4StandardModule
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/abstracts/PancakeSwapV4StandardModule.sol)

**Inherits:**
ReentrancyGuardUpgradeable, PausableUpgradeable, [IArrakisLPModule](/src/interfaces/IArrakisLPModule.sol/interface.IArrakisLPModule.md), [IArrakisLPModuleID](/src/interfaces/IArrakisLPModuleID.sol/interface.IArrakisLPModuleID.md), [IPancakeSwapV4StandardModule](/src/interfaces/IPancakeSwapV4StandardModule.sol/interface.IPancakeSwapV4StandardModule.md), ILockCallback

this module can set pancakeswap v4 pool that have a generic hook,
that don't require specific action to become liquidity provider.

*due to native coin standard difference between pancakeswap and arrakis,
we are assuming that all inputed amounts are using arrakis vault token0/token1
as reference. Internal logic of PancakeSwapV4StandardModule will handle the conversion or
use the poolKey to interact with the poolManager.*


## State Variables
### poolManager

```solidity
ICLPoolManager public immutable poolManager;
```


### vault

```solidity
IVault public immutable vault;
```


### distributor

```solidity
IDistributor public immutable distributor;
```


### collector

```solidity
address public immutable collector;
```


### _guardian

```solidity
address internal immutable _guardian;
```


### metaVault
module's metaVault as IArrakisMetaVault.


```solidity
IArrakisMetaVault public metaVault;
```


### token0
module's token0 as IERC20Metadata.


```solidity
IERC20Metadata public token0;
```


### token1
module's token1 as IERC20Metadata.


```solidity
IERC20Metadata public token1;
```


### isInversed
boolean to know if the poolKey's currencies pair are inversed.


```solidity
bool public isInversed;
```


### managerFeePIPS
manager fees share.


```solidity
uint256 public managerFeePIPS;
```


### oracle
oracle that will be used to proctect rebalances against attacks.


```solidity
IOracleWrapper public oracle;
```


### maxSlippage
max slippage that can occur during swap rebalance.


```solidity
uint24 public maxSlippage;
```


### poolKey
pool's key of the module.


```solidity
PoolKey public poolKey;
```


### ethWithdrawers
list of allowed addresses to withdraw eth.


```solidity
mapping(address => uint256) public ethWithdrawers;
```


### _init0

```solidity
uint256 internal _init0;
```


### _init1

```solidity
uint256 internal _init1;
```


### _ranges

```solidity
Range[] internal _ranges;
```


### _activeRanges

```solidity
mapping(bytes32 => bool) internal _activeRanges;
```


## Functions
### onlyManager


```solidity
modifier onlyManager();
```

### onlyMetaVault


```solidity
modifier onlyMetaVault();
```

### onlyGuardian


```solidity
modifier onlyGuardian();
```

### onlyMetaVaultOwner


```solidity
modifier onlyMetaVaultOwner();
```

### constructor


```solidity
constructor(
    address poolManager_,
    address guardian_,
    address vault_,
    address distributor_,
    address collector_
);
```

### pause

function used to pause the module.

*only callable by guardian*


```solidity
function pause() external whenNotPaused onlyGuardian;
```

### unpause

function used to unpause the module.

*only callable by guardian*


```solidity
function unpause() external whenPaused onlyGuardian;
```

### initialize

initialize function to delegate call onced the beacon proxy is deployed,
for initializing the uniswap v4 standard module.


```solidity
function initialize(
    uint256 init0_,
    uint256 init1_,
    bool isInversed_,
    PoolKey calldata poolKey_,
    IOracleWrapper oracle_,
    uint24 maxSlippage_,
    address metaVault_
) external initializer;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`init0_`|`uint256`|initial amount of token0 to provide to uniswap standard module.|
|`init1_`|`uint256`|initial amount of token1 to provide to uniswap standard module.|
|`isInversed_`|`bool`|boolean to check if the poolKey's currencies pair are inversed, compared to the module's tokens pair.|
|`poolKey_`|`PoolKey`|pool key of the uniswap v4 pool that will be used by the module.|
|`oracle_`|`IOracleWrapper`|address of the oracle used by the uniswap v4 standard module.|
|`maxSlippage_`|`uint24`|allowed to manager for rebalancing the inventory using swap.|
|`metaVault_`|`address`|address of the meta vault.|


### initializePosition

function used to initialize the module
when a module switch happen

*check if the pool is initialized.*


```solidity
function initializePosition(
    bytes calldata
) external virtual onlyMetaVault;
```

### withdrawEth

*left over will sit on the module.*


```solidity
function withdrawEth(
    uint256 amount_
) external nonReentrant whenNotPaused;
```

### approve


```solidity
function approve(
    address spender_,
    address[] calldata tokens_,
    uint256[] calldata amounts_
) external nonReentrant whenNotPaused onlyMetaVaultOwner;
```

### setPool

function used to set the pool for the module.


```solidity
function setPool(
    PoolKey calldata poolKey_,
    LiquidityRange[] calldata liquidityRanges_,
    SwapPayload calldata swapPayload_,
    uint256 minBurn0_,
    uint256 minBurn1_,
    uint256 minDeposit0_,
    uint256 minDeposit1_
) external onlyManager nonReentrant whenNotPaused;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`poolKey_`|`PoolKey`|pool key of the uniswap v4 pool that will be used by the module.|
|`liquidityRanges_`|`LiquidityRange[]`|list of liquidity ranges to be used by the module on the new pool.|
|`swapPayload_`|`SwapPayload`|swap payload to be used during rebalance.|
|`minBurn0_`|`uint256`|minimum amount of token0 to burn.|
|`minBurn1_`|`uint256`|minimum amount of token1 to burn.|
|`minDeposit0_`|`uint256`|minimum amount of token0 to deposit.|
|`minDeposit1_`|`uint256`|minimum amount of token1 to deposit.|


### withdraw

function used by metaVault to withdraw tokens from the strategy.


```solidity
function withdraw(
    address receiver_,
    uint256 proportion_
)
    public
    virtual
    onlyMetaVault
    nonReentrant
    returns (uint256 amount0, uint256 amount1);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`receiver_`|`address`|address that will receive tokens.|
|`proportion_`|`uint256`|number of share needed to be withdrawn.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 withdrawn.|
|`amount1`|`uint256`|amount of token1 withdrawn.|


### rebalance

function used to rebalance the inventory of the module.


```solidity
function rebalance(
    LiquidityRange[] memory liquidityRanges_,
    SwapPayload memory swapPayload_,
    uint256 minBurn0_,
    uint256 minBurn1_,
    uint256 minDeposit0_,
    uint256 minDeposit1_
)
    public
    onlyManager
    nonReentrant
    whenNotPaused
    returns (
        uint256 amount0Minted,
        uint256 amount1Minted,
        uint256 amount0Burned,
        uint256 amount1Burned
    );
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`liquidityRanges_`|`LiquidityRange[]`|list of liquidity ranges to be used by the module.|
|`swapPayload_`|`SwapPayload`|swap payload to be used during rebalance..|
|`minBurn0_`|`uint256`|minimum amount of token0 to burn.|
|`minBurn1_`|`uint256`|minimum amount of token1 to burn.|
|`minDeposit0_`|`uint256`|minimum amount of token0 to deposit.|
|`minDeposit1_`|`uint256`|minimum amount of token1 to deposit.|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0Minted`|`uint256`|amount of token0 minted.|
|`amount1Minted`|`uint256`|amount of token1 minted.|
|`amount0Burned`|`uint256`|amount of token0 burned.|
|`amount1Burned`|`uint256`|amount of token1 burned.|


### withdrawManagerBalance

function used by metaVault or manager to get manager fees.


```solidity
function withdrawManagerBalance()
    public
    nonReentrant
    whenNotPaused
    returns (uint256 amount0, uint256 amount1);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|amount of token0 sent to manager.|
|`amount1`|`uint256`|amount of token1 sent to manager.|


### setManagerFeePIPS

function used to set manager fees.

*default swapPayload, no swap happens here.
swapPayload will be empty. And will use it to do rebalance and collect fees.*


```solidity
function setManagerFeePIPS(
    uint256 newFeePIPS_
) external onlyManager whenNotPaused;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`newFeePIPS_`|`uint256`|new fee that will be applied.|


### receive


```solidity
receive() external payable;
```

### guardian

function used to get the address that can pause the module.


```solidity
function guardian() external view returns (address);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`<none>`|`address`|guardian address of the pauser.|


### getRanges

function used to get the list of active ranges.


```solidity
function getRanges() external view returns (Range[] memory ranges);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`ranges`|`Range[]`|active ranges|


### getInits

function used to get the initial amounts needed to open a position.


```solidity
function getInits()
    external
    view
    returns (uint256 init0, uint256 init1);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`init0`|`uint256`|the amount of token0 needed to open a position.|
|`init1`|`uint256`|the amount of token1 needed to open a position.|


### totalUnderlying

function used to get the amount of token0 and token1 sitting
on the position.


```solidity
function totalUnderlying()
    external
    view
    returns (uint256 amount0, uint256 amount1);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|the amount of token0 sitting on the position.|
|`amount1`|`uint256`|the amount of token1 sitting on the position.|


### totalUnderlyingAtPrice

function used to get the amounts of token0 and token1 sitting
on the position for a specific price.


```solidity
function totalUnderlyingAtPrice(
    uint160 priceX96_
) external view returns (uint256 amount0, uint256 amount1);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`priceX96_`|`uint160`|price at which we want to simulate our tokens composition|

**Returns**

|Name|Type|Description|
|----|----|-----------|
|`amount0`|`uint256`|the amount of token0 sitting on the position for priceX96.|
|`amount1`|`uint256`|the amount of token1 sitting on the position for priceX96.|


### validateRebalance

function used to validate if module state is not manipulated
before rebalance.


```solidity
function validateRebalance(
    IOracleWrapper oracle_,
    uint24 maxDeviation_
) external view;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`oracle_`|`IOracleWrapper`|oracle that will used to check internal state.|
|`maxDeviation_`|`uint24`|maximum deviation allowed. rebalance can happen.|


### managerBalance0

function used to get manager token0 balance.

*amount of fees in token0 that manager have not taken yet.*


```solidity
function managerBalance0()
    external
    view
    returns (uint256 managerFee0);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`managerFee0`|`uint256`|amount of token0 that manager earned.|


### managerBalance1

function used to get manager token1 balance.

*amount of fees in token1 that manager have not taken yet.*


```solidity
function managerBalance1()
    external
    view
    returns (uint256 managerFee1);
```
**Returns**

|Name|Type|Description|
|----|----|-----------|
|`managerFee1`|`uint256`|amount of token1 that manager earned.|


### _lockAcquired


```solidity
function _lockAcquired(
    Action action_,
    bytes memory data_
) internal returns (bytes memory);
```

### _internalRebalance


```solidity
function _internalRebalance(
    LiquidityRange[] memory liquidityRanges_,
    SwapPayload memory swapPayload_
)
    internal
    returns (
        uint256 amount0Minted,
        uint256 amount1Minted,
        uint256 amount0Burned,
        uint256 amount1Burned
    );
```

## Enums
### Action

```solidity
enum Action {
    WITHDRAW,
    REBALANCE,
    DEPOSIT_FUND
}
```

