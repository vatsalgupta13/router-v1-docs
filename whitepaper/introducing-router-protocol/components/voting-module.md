# Voting Module

### How and when is a proposal submitted to the destination chain?

Following the locking of funds, the bridge contract on the source chain emits an event that is picked up by the listener interface present on router nodes. Upon receiving the event, this function parses the event into a general bridge message and relays it to the router interface of the node, which in turn forwards the message to the writer. The writer converts the message to a valid proposal that is submitted on the target blockchain.

### How does the voting process work?

Once a proposal is created on the destination chain, other router nodes vote on it by signing the proposal. Once the voting threshold is achieved, Router Protocol's voting module runs a randomizer function to select a node to perform the executeProposal call. This is done to prevent multiple router nodes from calling the executeProposal function simultaneously. Although unlikely, if the selected node fails to execute this call, the voting module reruns the randomizer function, but this time it will exclude the node that failed to perform this task before.



Much like our [fee manager module](fee-manager-module.md), our voting module is completely modular and can be used by other developers in their projects without a lot of hassles.
