# Aggregator Contract

A dedicated contract that the ParaRouter calls to carry out the trades specified by the pathfinder algorithm. This contract is only called into effect during arbitrary (non-stablecoin) asset transfers. For stablecoin transfers, the ParaRouter directly calls the ERC20 handler.
