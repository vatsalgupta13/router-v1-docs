# State Channels

Using a state channel is a compelling approach for performing transactions off the base chain without the need for any additional trust between the network participants. To understand how state channels work, let us consider an example wherein a group of participants want to deploy a multiplayer game on the Ethereum blockchain. In such a game, network participants would be required to perform several actions in rapid succession, each of which would be counted as a transaction. If the game is deployed on Ethereum in a conventional manner, participants will need to pay gas costs each time they perform an action and will have to wait for the block to be mined before performing the following action. This would make the game both slow and expensive [\[5\]](../references.md#5-sam-richard.-state-channels.-https-ethereum.org-en-developers-docs-scaling-state-channels-may-2021). The application can be made much more efficient by using state channels, which can be implemented in three basic steps [\[6\]](../references.md#6-jeff-coleman.-state-channels.-https-www.jeffcoleman.ca-state-channels-november-2015.):&#x20;

**Step 1)** The game’s participants initialize a state on the Ethereum network by deploying a smart contract signed by all of them.&#x20;

**Step 2)** Whenever participants want to perform an action, they create and sign transactions, but instead of sending these transactions to be mined on the Ethereum blockchain, they simply update the state among themselves. Every time a new update takes place, it overrides the previous update.&#x20;

**Step 3)** Every network participant is allowed to make unlimited updates as long as they receive unanimous consent from all the other participants. Once the game ends, the participants submit the most recent state to the smart contract on the Ethereum network, and the changes as per the final state take effect.