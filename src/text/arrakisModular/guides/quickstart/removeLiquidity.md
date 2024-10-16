# Remove Liquidity

Here we explain how to remove liquidity from a Meta Vault that you own LP shares of.

1. Identify the Meta Vault address you want to exit, and verify it matches the address of your LP token. See for example [here](../../../modules/hotAmm/deployments.md) for a full list of deployment addresses related to HOT AMM.
2. From now on, we use the Arrakis Public Router contract, defined here
   [`ArrakisPublicVaultRouter.sol`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md)
3. Approve the LP token amount you want to burn and convert in the underlying tokens by using the standard ERC20 `Approve`. The approval must be to `ArrakisPublicVaultRouter`. Alternatively, you can set up Permit2 data and signature for a gasless approval transaction.
4. Prepare the [`RemoveLiquidityData`](../../technicalReference/routers/structs/struct.RemoveLiquidityData.md)
5. Depending on the approval type for the vault LP token, there are two paths:

- If you did an ERC20 approval, call [`removeLiquidity`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#removeliquidity).
- If you set up Permit2 Data and Signature, call [`removeLiquidityPermit2`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#removeliquiditypermit2)

6. You will receive `token0` and `token1` amounts correspondig to the amount of shares burned.
