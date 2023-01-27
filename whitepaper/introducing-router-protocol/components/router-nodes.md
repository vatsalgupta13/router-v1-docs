# Router Nodes

Router Protocol maintains a set of nodes that listen for events on the source chain, generate proposals for those events, and submit signed proposals on the destination chain as a vote. For a transfer to be accepted and sent across the bridge, it must receive enough votes to exceed a predetermined threshold. All the bridge contracts maintain a safe list of addresses so that votes received only from approved router nodes are taken into consideration. Each router node runs a Golang chain module that has four components:

* **Connector:** Responsible for connecting a router node to all chains which are a part of Router Protocol’s super mesh. A connector is shared by a node’s listener and writer.
* **Listener:** Actively observes chain state transitions to listen for initiated transfers. Whenever a transfer is detected, it constructs a message and passes it to the router interface. The message has a total of 6 parameters: source chain ID, destination chain ID, resource ID, transfer type (fungible transfer, non-fungible transfer or generic transfer), deposit nonce, and payload (data for the specific transfer).
* **Router:** Receives constructed messages from listeners and forwards them to the writer.
* **Writer:** Responsible for parsing the bridge message into a valid transaction and submitting it to the destination chain.

![Figure 3: Architecture of a Router Node](<../../../.gitbook/assets/Router Node.png>)
