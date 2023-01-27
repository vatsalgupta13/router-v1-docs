# Chains

These are blockchain networks that are a part of Router's liquidity 'super mesh.' The chain where a transaction is initiated is referred to as the source chain, while the chain where the transaction is executed is called the target chain. During a cross-chain transfer, Router Protocol locks users' funds on the source chain and releases them on the target chain. To facilitate these transfers, there are two crucial specifications associated with each chain:&#x20;

* **Chain ID:** A unique 8-bit identifier used to identify a chain.&#x20;
* **Resource ID:** A 32-byte identifier used to map actions on the source chain with actions on the destination chain. The least significant byte of a resource ID includes the chain ID from where the transaction is initiated, while the remaining 31 bytes can be used to represent any mapping. For example, the resource ID is used by Router Protocol to represent token mappings between different chains.
