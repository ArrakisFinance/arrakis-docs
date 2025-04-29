# Arrakis Pro Vault Setup

### Deployment

For now simply [contact us](https://qxqhpatmzz7.typeform.com/to/IZdNgmmM?typeform-source=arrakis.finance) to have an Arrakis engineer deploy an Arrakis Pro vault on your behalf. (If you really want to deploy by yourself and know what you're doing, see [deploy scripts here](https://github.com/ArrakisFinance/arrakis-modular/tree/main/script))

At deployment you choose what initial **module** your vault uses. See [integrations](../../text/arrakisPro/integrations/overview.md) section.

### Deposit

After deployment, you can now deposit liquidity into your Arrakis Pro vault. Navigate to your vault owner Safe on [Safe App](https://app.safe.global). Then go to `Apps -> My custom apps` and then add `https://app.arrakis.finance/pro` as a "Custom Safe App". In the custom safe app you'll see your Pro vault(s) and can use the GUI to deposit with one multi-step Safe transaction.

### Manual Deposit

If you want or need to deposit manually here are the low-level steps:

1. From `vault.owner()` acct -> call [whitelistDepositors](../../text/arrakisModular/technicalReference/metaVaults/privateVaults/contract.ArrakisMetaVaultPrivate.html#whitelistdepositors) on your Vault contract to whitelist the account that will deposit the tokens.

2. From `whitelisted depositor` acct -> approve `vault.module()` contract as spender of token(s) you will deposit.

3. From `whitelisted depositor` acct -> Call [deposit](../../text/arrakisModular/technicalReference/metaVaults/privateVaults/contract.ArrakisMetaVaultPrivate.html#deposit) on your Vault contract to deposit funds. (If depositing native ETH remember to pass a `msg.value` that matches the amount0/1 argument)

### Activation

After deposit your vault is not necessarily activated immediately. To activate your vault and deploy LP into the DEX of interest, you'll need a "strategy config" set on the Arrakis Pro Backend. See [strategies](../../text/arrakisPro/strategies/overview.md) section.

