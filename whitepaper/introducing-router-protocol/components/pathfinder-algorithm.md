# Pathfinder Algorithm

Router uses a proprietary pathfinder algorithm to find the optimal route to move assets from the source chain to the destination chain. Pathfinder algorithm is called directly by Router’s UI and takes in four parameters:

* **Chain ID:** Instructs the pathfinder to access DEX protocols on a particular chain. Pathfinder algorithm maintains a list of DEX contract addresses mapped to each chain ID.&#x20;
* **fromTokenAddress:** ERC20 token address of the asset to be sold.&#x20;
* **toTokenAddress:** ERC20 token address of the asset to be bought.&#x20;
* **Amount:** The number of tokens that need to be traded.

Based on these parameters, the pathfinder creates a JSON object which includes the optimal route for the swap and returns it to Router’s UI, which forwards the object to the bridge contract on the source chain.
