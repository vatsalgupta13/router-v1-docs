# Architecture

Unlike traditional deployments of cross-chain protocols, which use 1-to-1 bridges, Router creates a mesh network where all chains are connected to each other via the same set of router nodes (refer to fig. 4). These nodes can listen to and write transactions on all blockchains that are part of Router's super mesh. Any new chain can therefore be simply plugged into Router's super mesh by pushing its relevant configurations to all the router nodes.

![Figure 4: Router's Architecture](<../../.gitbook/assets/router architecture (1)-01.png>)
