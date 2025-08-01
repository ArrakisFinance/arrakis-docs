# Quickstart: Public Vaults

To make the deposit process safe and simple we created the [Arrakis Public Vault Router V2](../../../text/arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md). This contract is in charge of getting the right amounts and tokens to deposit, as well as containing convenient functions with the ability to wrap assets and swap atomically before deposit. It also integrates the Permit 2 standard for gassless approvals.

### Add Liquidity

The following provides a step-by-step explanation of depositing liquidity into an Arrakis Public Vault via the Router.

1. Identify the Meta Vault associated to the pair you want to participate in.

2. Next step is use the Router to determine how many of each tokens you expect to need to join the Meta Vault.

   - Use [`getMintAmounts`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#getmintamounts) to determine the extact amounts of `token0` and `token1` you expect to deposit, given the maximum of each token you'd like to provide.

3. In order to set token transfer authorizations before depositing, there are two alternatives:

   - Calling the standard ERC20 `Approve` (approve `<router>` to spend)
   - Set up Permit2 data and signature

4. Now, in order to deposit into the pool there are multiple paths:

   - If you set up ERC20 approvals:

     - Call [`addLiquidity`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#addliquidity) to deposit both tokens to the vault.
     - If you have `ETH` and want to deposit into a pool with `WETH` as one of its tokens, you can also call [`wrapAndAddLiquidity`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#wrapandaddliquidity).
     - If you want to synchronously perform a swap before adding liquidity you can call [`swapAndAddLiquidity`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#swapandaddliquidity) or [`wrapAndSwapAndAddLiquidity`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#wrapandswapandaddliquidity) (if you want to use send native `ETH` instead of `WETH` for a swap-and-deposit interaction)

   - If you have set the correct Permit2 data and signature you should respectively call [`addLiquidityPermit2`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#addliquiditypermit2),
     [`wrapAndAddLiquidityPermit2`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#wrapandaddliquiditypermit2), [`swapAndAddLiquidityPermit2`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#swapandaddliquiditypermit2) or [`wrapAndSwapAndAddLiquidityPermit2`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#wrapandswapandaddliquiditypermit2)

5. Once your deposit transaction goes through, you obtain ERC20 LP `shares` of the vault you are depositing to.

### Remove Liquidity

Removing Liquidity from an Arrakis Public Vault that you hold LP tokens of is easy.

1. Ensure you have LP `shares` of the Meta Vault you want to withdraw from.

2. Determine how many shares you want to burn to withdraw liquidity. You can burn a partial amount or your entire balance.

3. In order to set token transfer authorizations for your LP tokens, there are two alternatives:

   - Calling the standard ERC20 `Approve` on your LP tokens (approve `<router>` to spend your shares)
   - Set up Permit2 data and signature for your LP tokens

4. Now, in order to withdraw from the pool there are two paths:

   - If you set up ERC20 approvals:

     - Call [`removeLiquidity`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#removeliquidity) to burn your LP tokens and receive the underlying `token0` and `token1`.

   - If you have set the correct Permit2 data and signature you should call [`removeLiquidityPermit2`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouterV2.md#removeliquiditypermit2)

5. Once your withdrawal transaction goes through, your LP `shares` are burned and you receive the proportional amounts of the underlying `token0` and `token1` directly to your specified receiver address.
