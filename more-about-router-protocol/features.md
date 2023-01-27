# Features

<details>

<summary>1) Any token to any token swap across chains</summary>

With Router Protocol, you can convert any asset A on chain X to asset B on chain Y. For e.g., you can swap SHIBA on Polygon for CAKE on BSC.

</details>

<details>

<summary>2) Flexibility in fees</summary>

Users can pay Router's transaction fees in either (a) the source chain's native gas token, (b) $USDC, or (c) $ROUTE/$DFYN tokens. As an added incentive for our community, users will receive a 50% discount on fees paid in $ROUTE and a 20% discount on fees paid in $DFYN tokens.

</details>

<details>

<summary>3) Modular mesh network instead of 1-to-1 bridges</summary>

Router Protocol is building a mesh network to connect various blockchain networks. Compared to the existing deployments of 1-to-1 bridges, which function as dedicated links between two chains, a mesh network is more extensible.

</details>

<details>

<summary>4) Cross-chain settlement engine</summary>

Router Protocol ensures no blocking for user funds and guarantees settlements of all transactions.

</details>

<details>

<summary>5) Proprietary pathfinder algorithm to ensure the best price swaps</summary>

Router uses a pathfinder algorithm to find the most optimal route for cross-chain swaps.&#x20;

</details>

<details>

<summary>6) Plug and play for developers</summary>

Router Protocol will allow developers to leverage its SDK to build complex cross-chain blockchain applications.

**Example:** You can create a cross-chain farming engine that allows you to stake on an Ethereum protocol while using funds from your Polygon wallet, i.e., you do not need to bridge funds to Ethereum and then stake on the said Ethereum protocol, Router will abstract that process for you. You can also borrow on a chain with a low-interest rate and lend on a chain with a higher interest rate, all while sitting on a single chain. Mesh Network: Router is building a many-to-many mesh network that allows seamless data flow between various chains, unlike traditional one-to-one bridges where one requires a dedicated link between two chains.

</details>

<details>

<summary>7) AMM fallback</summary>

To allow cross-chain asset transfers without creating any fragmentation, Router Protocol uses Dfyn AMM as a fallback reserve in case of stable asset scarcity. Router can plug into any AMM or DEX, but it is optimized to work with our in-house DEX, Dfyn Exchange, to ensure the finality of a transaction.&#x20;

</details>

<details>

<summary>8) Isolated execution module</summary>

Router executes transactions on a stateless execution pallet that can avoid direct interaction with the bridge reserves. Keeping the reserves isolated from the execution environment will prevent any malicious entities from accessing the reserve funds.&#x20;

</details>
