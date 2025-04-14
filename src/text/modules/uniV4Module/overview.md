# Uniswap v4 Module

Uniswap v4 introduces significant enhancements, focusing on flexibility and efficiency. One of the key features is the introduction of **hooks**, which are customizable smart contract functions. These hooks allow developers to modify pool behavior at specific points of the call lifecycle. This flexibility allows for more sophisticated LP strategies, MEV protection and better adaptation to market conditions.

Additionally, Uniswap v4 includes gas optimizations that reduce transaction costs by consolidating operations and optimizing core protocol logic. The adoption of a singleton contract architecture further reduces deployment costs and simplifies upgrades. The possibility native ETH instead of Wrapped ETH, allows for further gas reductions, which is critical to attract more trading volumes.

Arrakis Pro offers a module to connect to any pool with any enabled hook in Uniswap v4. The liquidity provision is powered by Arrakis Strategies, which aim to improve capital efficiency and reduce price impact for traders, all while reducing risks for LPs.