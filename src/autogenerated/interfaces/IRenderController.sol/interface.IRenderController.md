# IRenderController
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/interfaces/IRenderController.sol)


## Functions
### setRenderer

function used to set the renderer contract adress

*only the owner can do it.*


```solidity
function setRenderer(address renderer_) external;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`renderer_`|`address`|address of the contract that will render the tokenUri for the svg of the nft.|


### isNFTSVG

*for knowning if renderer is a NFTSVG contract.*


```solidity
function isNFTSVG(address renderer_) external view returns (bool);
```

### renderer

NFTSVG contract that will generate the tokenURI.


```solidity
function renderer() external view returns (address);
```

## Events
### LogSetRenderer

```solidity
event LogSetRenderer(address newRenderer);
```

## Errors
### InvalidRenderer

```solidity
error InvalidRenderer();
```

### AddressZero

```solidity
error AddressZero();
```
