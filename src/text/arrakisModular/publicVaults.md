# Public Vault List

## Ethereum Mainnet

### WETH/USDC Vault

This is the first and flagship Arrakis Modular Public Vault.

- Network: `Ethereum Mainnet`
- Vault Address: [`0xf790870ccF6aE66DdC69f68e6d05d446f1a6ad83`](https://etherscan.io/address/0xf790870ccF6aE66DdC69f68e6d05d446f1a6ad83)
- Type: `ERC20`
- Symbol: `ARRAKIS`
- Active Module: [`HOT AMM`](../modules/hotAmm/overview.md)
- Whitelisted Modules: [`HOT AMM`](../modules/hotAmm/overview.md), [`Bunker]() (safety module)
- Vault Owner (Timelock): [`0xCFaD8B6981Da1c734352Bd31618040C23FE99117`](https://etherscan.io/address/0xCFaD8B6981Da1c734352Bd31618040C23FE99117)
- Vault Timelock Admin: [`0x5108EF86cF493905BcD35A3736e4B46DeCD7de58`](https://etherscan.io/address/0x5108EF86cF493905BcD35A3736e4B46DeCD7de58) (Arrakis Multisig)

Management Configuration:

- Vault Executor: [`0x030DE9fd3ca63AB012f4E22dB595b66C812c8525`](https://etherscan.io/address/0x030DE9fd3ca63AB012f4E22dB595b66C812c8525) (HOTExecutor)
- Price Oracle: [`0xF23d83Da92844C53aD57e6031c231dC93eC4eE80`](https://etherscan.io/address/0xF23d83Da92844C53aD57e6031c231dC93eC4eE80) (Wrapped `Chainlink` feeds)
- Cooldown Period: `60 seconds`
- Max Oracle Deviation: `2%`
- Max Swap Slippage: `2%`
- Manager Fee (on Swap Fees Earned): `1%`


HOT AMM pool WETH/USDC Config:

- QuoteSigner: `0x498c8a1a179b5D1D4Ff64bC90Cf3224a3478765C` (controlled by Arrakis)
- HOT Manager: [`0xAf6f9640092cB1236E5DB6E517576355b6C40b7f`](https://etherscan.io/address/0xAf6f9640092cB1236E5DB6E517576355b6C40b7f) (timelocked)
- Price Oracle: `Chainlink`
- Max HOT Swaps Per Block: `3`
- Max HOT Swap Oracle Deviation: `3.5%`

Note On Quoter "HOT Dynamic Fee Oracle" Activity:

For now, we are focused on the core RfQ mechanism of the HOT AMM and are taking a conservative pproach to permissionless swaps through the AMM. The AMM Swap Fee will quickly rise from `0.1%` to `2.5%` for swaps in both directions at a rate of `0.01%` per second.


