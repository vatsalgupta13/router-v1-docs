# Dedicated Chain to Host Aggregator Infrastructure

To ensure high throughput while maintaining protocol security, Router will initially operate under a trusted federation model, i.e., the validation mechanism will only be partially decentralized. However, in keeping with the ethos of DeFi, Router will eventually move to a fully decentralized model. To achieve this, Router will host a dedicated blockchain that will act as a hub between various blockchains. This blockchain will be built using the Cosmos SDK and operate on the tendermint consensus algorithm. Once deployed, all cross-chain operations will be verified on this chain, with all the processes transparently open for everyone to see. By virtue of having a dedicated chain, Router will also be able to maintain a decentralized account of all the assets that have been transferred/mapped across different chains. This account will be updated trustlessly after the successful completion of each transaction.

### Router Protocol as an Application-Specific Chain

Building Router as an application-specific chain on the cosmos ecosystem will enable:

1. Transparent accounting over all the actions carried out by the protocol;&#x20;
2. easier integration with other blockchains;
3. the use of Cosmos' governance framework for an easier decision-making process.

### Router Protocol <> Cosmos IBC

Router protocol can enable interoperability between various chains in the Cosmos ecosystem and   EVM-based chains by leveraging the functionality of IBC and linking it with Router's existing infrastructure.
