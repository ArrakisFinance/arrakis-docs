# Integrations

One key feature of Arrakis Modular is the ability to switch between **modules**, where each module defines the vault's integration with a liquidity consuming dApp. For Arrakis Pro there are currently four potential **modules** to choose from:

1. [Uniswap V4](../../text/modules/uniV4Module.md): Supply liquidity to Uniswap V4 with easy batching of liquidity operations on a single pool. Easily migrate token0/token1 liquidity across safe (no hook logic on add or remove liquidity) pools (hooks). Integrates with merkl rewards so that vault LPs can earn them.

2. [Uniswap V3](): Supply liquidity and receive trading fees on a single Uniswap pool, with direct mint and burns for maximum efficiency.

3. [Aerodrome Staked](../../text/modules/aerodromeModule.md): Supply liquidity and stake liquidity positions to earn AERO on a single Aerodrome slipstream pool, with easy batching of NFT liquidity position operations (mint, burn, claim rewards).

4. [Aerodrome Fees](): Identical to Uniswap V3 Module, but with slight changes on the interface to support Aerodrome Slipstream pools.

5. [PancakeSwap Infinity](../../text/modules/pancakeModule.md): [identical in features to Uniswap V4 module, but code is different]

6. [PancakeSwap V3](): Supply liquidity and stake liquidity positions to earn CAKE on a single PancakeSwap V3 pool, with easy batching of NFT liquidity position operations (mint, burn, claim rewards).

7. [Velodrome](../../text/modules/velodromeModule.md): [identical to Aerodrome module, same bytecode]

Because each of these modules use Uniswap V3 style tick math they can all consume the same core strategy templates (with slightly different paylaod encodings) described in the [strategies](../../text/arrakisPro/strategies/overview.md) section.
