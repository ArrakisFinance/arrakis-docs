# Price Oracles

All Arrakis Vaults have a concept of a `price oracle` set by vault owners on the [ArrakisStandardManager](./technicalReference/metaVaults/core/contract.ArrakisStandardManager.md). These price oracles are used as a third-party check on `executor` management calls to a vault.

We use our own standard interface for oracle reads and thus we can seamlessly integrate any type of onchain oracle price feed no matter the interfaces/patterns (RedStone, Chainlink, Uni V3 TWAP, etc) -- just by defining a simple Oracle Wrapper smart contract.

To accelerate the integration of safe public and private Meta Vaults for newer tokens that may not already have performant oracle feeds onchain, we refer clients to our oracle partner [RedStone](https://redstone.finance/).

## Methodology

Arrakis implements a standard oracle interface that must be followed:

```solidity
interface IOracleWrapper {
    /// @notice function used to get price0.
    /// @return price0 price of token0/token1.
    function getPrice0() external view returns (uint256 price0);

    /// @notice function used to get price1.
    /// @return price1 price of token1/token0.
    function getPrice1() external view returns (uint256 price1);
}
```

Any smart contract that utilizes this interface can function as an oracle on the Arrakis standard manager. This interface is consumed during [ArrakisStandardManager.rebalance](./technicalReference/metaVaults/core/contract.ArrakisStandardManager.md#rebalance) here:

```solidity
        uint256 price0 = info.oracle.getPrice0();

        uint256 vaultInToken1BeforeRebalance = FullMath.mulDiv(
            amount0, price0, 10 ** token0Decimals
        ) + amount1;
```

we store `vaultInToken1BeforeRebalance` and then compare it to the value after rebalance. Further checks can be implemented at the module level with oracle price feeds thanks to this call here:

```solidity
    module.validateRebalance(info.oracle, info.maxDeviation);
```
