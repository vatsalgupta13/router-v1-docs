# Problems with Existing Solutions

The problem of blockchain interoperability has become harder to ignore as more siloed ecosystems emerge across the DeFi space. To solve this issue, multiple bridging technologies have emerged in recent times. Some of the issues that are prevalent across most of these technologies are delineated below:

### Existing bridges are 1-to-1

Most of the current crop of cross-chain infrastructures rely on 1-to-1 bridges to build a network of multiple chains (refer to the fig. below). Such a model lacks extensibility since it requires the addition of `N` separate bridges each time a new chain has to be added (where `N` denotes the number of chains in the network). This leads to a discrepancy in cost, connectivity, and value transfer.

![Figure 2: Legacy Architecture](<../.gitbook/assets/Legacy Architecture.png>)

### State Dependency

Currently, most protocols are limited only to ERC20 states. However, there is a growing need for cross-chain states across a range of applications like:&#x20;

* NFTs (ERC721)&#x20;
* DeFi Application States (Contract-level arbitrary data)

### Lack of Transparent Accounting

There is no clear and public record of all the transactions going through the bridges. Also, there is no way to verify the state transitions from one blockchain to another.



{% hint style="info" %}
Some of the earliest models to enable cross-chain operations were Hash Time-locked Contracts (HTLCs) and sidechains. To read more about them, kindly refer to our appendices:
{% endhint %}

{% content-ref url="appendices/hash-time-locked-contracts-htlcs.md" %}
[hash-time-locked-contracts-htlcs.md](appendices/hash-time-locked-contracts-htlcs.md)
{% endcontent-ref %}

{% content-ref url="appendices/relays-sidechains.md" %}
[relays-sidechains.md](appendices/relays-sidechains.md)
{% endcontent-ref %}
