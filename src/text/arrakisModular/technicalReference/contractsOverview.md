# Arrakis Modular Smart Contracts

## Metavaults

### Vaults

`abstracts/ArrakisMetaVault.sol` This contract is the core of the minimal Arrakis Meta Vault standard. It encodes the interfaces and patterns of an Arrakis Meta Vault. A functional ArrakisMetaVault has a `module` contract connected to it which entirely defines how the vault integrates with an underlying Liquidity Provision protocol, using standard interfaces. This contract is abstract because it is extended to expose the differenced in the Public and Private vault type, most notable how they are tokenized and how the deposit function is implemented.

- `ArrakisMetaVaultPublic.sol` This inherits and extends the abstract `ArrakisMetaVault.sol` to create the ERC20 wrapped “public” Arrakis Meta Vault. If we want to create a shared LP position/strategy which can configure or delegate LP active management on behalf of all participants, then we’ll deploy an instance of this through the Factory contract. Public Vault deployments are permissioned since sensitive security parameters for multiple parties are under the timelocked control of a vault owner, so we want some ability to control who might deploy/configure/own these public vaults. Eventually this authority would be under the control of the “Arrakis DAO.”

- `ArrakisMetaVaultPrivate.sol` This inherits and extends the abstract `ArrakisMetaVault.sol` to create the “private” Arrakis Meta Vault, where only the vault owner controls adding or removing liquidity. If you want to create an LP management contract for your own private liquidity (we call this PALM for _private active liquidity management_) you’d deploy an instance of this through the Factory contract. Ownership is not timelocked and deployment is permissionless in this case, since the sensitive security parameters are fundamentally under the control of the custodian of the vault funds (i.e. the owner is the user).

### Factory

`ArrakisMetaVaultFactory.sol` deploys fresh instances of `ArrakisMetaVaultPublic` and `ArrakisMetaVaultPrivate` public vault deployments are permissioned, but private vault ones are not. Stores complete list of all vaults deployed, by type.

### Ownership

`PrivateVaultNFT.sol` an NFT contract that allows ownership of private vaults to each be tokenized and thus transferrable. Very standard NFT contract

## Modules

`abstract/ModuleRegistry.sol` this abstract contract handles the simple duty of “module” whitelistsing, so only modules deemed safe and correct can be used by vaults.

- `ModulePrivateRegistry.sol` registry of all modules which can be whitelisted and used by private vaults.

- `ModulePublicRegsitry.sol` registry of all modules which can be whitelisted and used by public vaults.

### Implementations

`modules/ValantisSOTModule.sol` This is the first ArrakisMetaVault module we will put into production, integrating a specific Sovereign Pool type of the new Valantis DEX.

## Administration

`ArrakisStandardManager.sol` The manager contract that adds additional safety checks to make delegated LP management safe and as trustless as possible. Arrakis will use this as the entry point to actively manage both private vaults and public vaults. Also how we confiuge/harvest manager fee collection for Arrakis protocol to take cut of revenues generated.

## Routing

`ArrakisPublicVaultRouter.sol` A router contract which integrates permit2 which helps depositors add liquidity to `ArrakisMetaVaultPublic` instances, safely and conveniently.

`RouterSwapExecutor.sol` a sub-component of the Public Vault Router used for swapping safely (need the middleman contract here for security concerns on these generic low level swaps being abused)

## Security

`Guardian.sol` this contract is in charge of a rushing pauser role who can pause parts of the system in the case of critical error/vulnerability. This authority would be ultimately in the hands of some “Guardian Multisig” much like how AAVE works today. For any upgradeable contracts (modules are all beacon proxies and could potentially be upgradeable) there would be a timelock. So pauses are rushing but upgrades are slow.

`TimeLock.sol` a slightly modified generic timelock (so that timelock cannot transfer ownership of the vault away from the timelock contract) a fresh instance of this is used for each Public Arrakis vault to make sure that security parameters cannot be rushingly reconfigured by a compromised public vault owner to extract value from the public vault.
