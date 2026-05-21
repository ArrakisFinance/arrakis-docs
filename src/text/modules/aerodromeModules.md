# Aerodrome Modules

We offer 2 Aerodrome Module integrations of Aerodrome Slipstream (concentrated liquidity) DEX.

## Aerodrome Staked Module

Vault Type(s): Private Vault

Features:

- manage multiple concentrated liquidity positions in a aggregated/batched way with nice interfaces
- Automatically stake all LP positions to earn AERO rewards
- configure and control automated LP strategies tailor designed for Aerodrome (and AERO capture)
- only available for pairs of Aerodrome whitelisted tokens
- optionally enable direct RFQ with the vault (policed by your oracle of choice)

See full contract specification [here](../../text/arrakisModular/technicalReference/modules/implementations/contract.AerodromeStandardModulePrivate.md)

## Aerodrome Fees Module

Vault Type(s): Private Vault

Features:

- manage multiple concentrated liquidity positions in a aggregated/batched way with nice interfaces
- get trading fees based on volumes (protocol fee is up to 10%)
- configure and control automated LP strategies tailor designed for Aerodrome
- available for all pairs of tokens
- optionally enable direct RFQ with the vault (policed by your oracle of choice)

## Deployments

Networks: Base (only)
