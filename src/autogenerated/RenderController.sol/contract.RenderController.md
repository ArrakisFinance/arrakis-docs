# RenderController
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/b9ae3a6dd7145e0f69f817dcb31abd79f8e19310/src/RenderController.sol)

**Inherits:**
Ownable, [IRenderController](/src/interfaces/IRenderController.sol/interface.IRenderController.md), Initializable


## State Variables
### renderer

```solidity
address public renderer;
```


## Functions
### initialize


```solidity
function initialize(address owner_) external initializer;
```

### setRenderer

function used to set the renderer contract

*only the svgController can do it.*


```solidity
function setRenderer(address renderer_) external onlyOwner;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`renderer_`|`address`|address of the contract that will render the tokenUri for the svg of the nft.|


### isNFTSVG


```solidity
function isNFTSVG(address renderer_) public view returns (bool);
```

