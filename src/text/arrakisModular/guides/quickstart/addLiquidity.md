# Add Liquidity

As we explained in the previous section, depositors who wish to provide liquidity to a Public Meta Vault must do it with both tokens in the pool and in the current proportion of the reserves. To simplify this process and improve the user experience we have designed a Public Router. This contract is in charge of getting the right amounts and tokens to deposit. This is achieved by integrating with a swap aggregator and wrapping tokens when necessary. It also implements the Permit 2 standard for gassless approvals.

The following guide provides a step-by-step explanation of adding liquidity by uisng our router.

1. Identify the Meta Vault associated to the pair you want to participate in. See for example [here](../../../modules/hotAmm/deployments.md) for a full list of deployment addresses related to HOT AMM.
2. From now on, we use the Arrakis Public Router contract, defined here
   [`ArrakisPublicVaultRouter.sol`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md)
3. Next step is to determine how many of each tokens are needed to join the Meta Vault. There are several options:
   - Use [`getMintAmounts`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#getmintamounts) to determine the extact amounts of `token0` and `token1` to deposit.
   - If you own only one of the tokens, you can either swap on your own to match the amounts needed, or you can use the buil-in swap features in `ArrakisPublicVaultRouter`.
     In the latter, only one token needs to be authorized.
4. In order to set token transfer authorizations before depositing, there are two alternatives:
   - Calling the standard ERC20 `Approve`
   - Set up Permit2 data and signature
5. Now, in order to deposit into the pool there are multiple paths:

   - If you set up ERC20 approvals:

     - Call [`addLiquidity`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#addliquidity) to deposit both tokens to the vault.
     - If you have `ETH` and want to deposit into a pool with `WETH` as one of its tokens, you can also call [`wrapAndAddLiquidity`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#wrapandaddliquidity).
     - If you have only one of the tokens in the pair, you can call [`swapAndAddLiquidity`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#swapandaddliquidity)
     - If you only have `ETH` and want to deposit into a pool with `WETH` as one of its tokens, you can call [`wrapAndSwapAndAddLiquidity`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#wrapandswapandaddliquidity)

   - If you have set the correct Permit2 data and signature you should respectively call [`addLiquidityPermit2`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#addliquiditypermit2),
     [`wrapAndAddLiquidityPermit2`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#wrapandaddliquiditypermit2), [`swapAndAddLiquidityPermit2`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#swapandaddliquiditypermit2) or [`wrapAndSwapAndAddLiquidityPermit2`](../../technicalReference/routers/contract.ArrakisPublicVaultRouter.md#wrapandswapandaddliquiditypermit2)

6. Once your deposit transaction goes through, you obtain ERC20 LP `shares` of the vault you are depositing to.
