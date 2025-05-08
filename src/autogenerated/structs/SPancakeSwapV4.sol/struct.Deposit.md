# Deposit
[Git Source](https://github.com/ArrakisFinance/arrakis-modular/blob/main/src/structs/SPancakeSwapV4.sol)


```solidity
struct Deposit {
    address depositor;
    uint256 proportion;
    uint256 value;
    bool notFirstDeposit;
    uint256 fee0;
    uint256 fee1;
    uint256 leftOverToMint0;
    uint256 leftOverToMint1;
}
```

