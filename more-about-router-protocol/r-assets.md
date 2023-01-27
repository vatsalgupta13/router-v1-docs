# R-Assets

### What are R-Assets?

R-Assets are Router Protocol's wrapped assets that function as a representation token or a proof, akin to an LP token. These assets maintain 1:1 mapping with their underlying assets since one "R-Asset" can only be minted if one "Asset" is locked. Let us consider USDC and RUSDC. Router can only mint a RUSDC when it has a USDC successfully locked in its reserve. This means that the number of RUSDC in circulation is always equal to the number of USDC locked in Router's bridge reserves.

### Does Router Protocol create a wrapped version of all tokens?

No. Router only creates a wrapped version of tokens that fall under the category of [reserve assets](transfer-flows.md), i.e. assets whose liquidity is actively maintained by Router. Currently, Router supports three R-Assets:

* RBNB (underlying asset - BNB)
* RMATIC (underlying asset - MATIC)
* RUSDC (underlying asset - USDC)
* RAVAX (underlying asset - AVAX)
* RFTM (underlying asset - FTM)
* RONE (underlying asset - ONE)
* RCRO (underlying asset - CRO)
* RETH (underlying asset - ETH)
* RROUTE (underlying asset - ROUTE)
* RDFYN (underlying asset - DFYN)

Since R-Assets can be minted/burnt by Router, cross-chain transactions involving these R-Assets will be much faster and cheaper (since no DEX interaction is required).&#x20;

### How do I receive these R-Assets?

Users will receive R-Asset whenever they provide liquidity of "Asset" to the Router bridge. For example, users will receive RBNB in exchange for staking BNB on Router's bridge contracts.

{% hint style="info" %}
It is important to note that users might inadvertently receive R-Assets while swapping assets between two chains. This is an edge case that occurs only when there is insufficient liquidity on the destination chain.
{% endhint %}

### What is the utility of these R-Assets?

R-Assets can be pooled with their underlying Assets to create R-Asset/Asset LP tokens on Dfyn. Users can then use these LP tokens to participate in R-Asset/Asset farm to earn liquidity mining rewards. For example, users can pool their RUSDC with USDC on Dfyn and participate in the RUSDC/USDC farm.

### How can I redeem my R-Asset for its underlying Asset?

Redeeming R-Asset for its underlying Asset is a fairly straightforward process. The step-by-step guide for the same can be found [here](../how-to/redeem-r-asset-for-asset.md).
