# Liquidity Pools

Router can plug into liquidity pools present across any DEX protocol. In the case of non-reserve asset transfers, Router will make use of these pools on the source chain to swap user-submitted asset to a stablecoin asset and on the target chain to swap stablecoin asset to user-desired asset. The DEX offering the best price, and the least slippage will be used to complete the order.
