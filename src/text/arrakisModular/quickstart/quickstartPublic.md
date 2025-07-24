# Quickstart: Public Vaults

To make the deposit process safe and simple we created the [Arrakis Public Vault Router](../../../text/arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md). This contract is in charge of getting the right amounts and tokens to deposit, as well as containing convenient functions with the ability to wrap assets and swap atomically before deposit. It also integrates the Permit 2 standard for gassless approvals.

### Add Liquidity

The following provides a step-by-step explanation of depositing liquidity into an Arrakis Public Vault via the Router.

1. Identify the Meta Vault associated to the pair you want to participate in. See for example [here](../../arrakisModular/publicVaults.md) for a list of Public Vaults.

2. Next step is use the Router to determine how many of each tokens you expect to need to join the Meta Vault.

   - Use [`getMintAmounts`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md#getmintamounts) to determine the extact amounts of `token0` and `token1` you expect to deposit, given the maximum of each token you'd like to provide.

3. In order to set token transfer authorizations before depositing, there are two alternatives:

   - Calling the standard ERC20 `Approve` (approve `<router>` to spend)
   - Set up Permit2 data and signature

4. Now, in order to deposit into the pool there are multiple paths:

   - If you set up ERC20 approvals:

     - Call [`addLiquidity`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md#addliquidity) to deposit both tokens to the vault.
     - If you have `ETH` and want to deposit into a pool with `WETH` as one of its tokens, you can also call [`wrapAndAddLiquidity`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md#wrapandaddliquidity).
     - If you want to synchronously perform a swap before adding liquidity you can call [`swapAndAddLiquidity`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md#swapandaddliquidity) or [`wrapAndSwapAndAddLiquidity`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md#wrapandswapandaddliquidity) (if you want to use send native `ETH` instead of `WETH` for a swap-and-deposit interaction)

   - If you have set the correct Permit2 data and signature you should respectively call [`addLiquidityPermit2`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md#addliquiditypermit2),
     [`wrapAndAddLiquidityPermit2`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md#wrapandaddliquiditypermit2), [`swapAndAddLiquidityPermit2`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md#swapandaddliquiditypermit2) or [`wrapAndSwapAndAddLiquidityPermit2`](../../arrakisModular/technicalReference/routers/contract.ArrakisPublicVaultRouter.md#wrapandswapandaddliquiditypermit2)

5. Once your deposit transaction goes through, you obtain ERC20 LP `shares` of the vault you are depositing to.

### Remove Liquidity

Removing Liquidity from an Arakis Public Vault that you hold LP tokens of is easy.

Simply call the [burn](../technicalReference/metaVaults/publicVaults/contract.ArrakisMetaVaultPublic.md#burn) directly on an Arrakis Meta Vault Public contract to burn `amount` of LP tokens that you hold and remit two-sided underlying (token0 and token1) to your `receiver` address of choice.
