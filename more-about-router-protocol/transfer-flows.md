# Transfer Flows

While bridging funds, Router Protocol treats every asset as belonging to one of the following three categories:

{% tabs %}
{% tab title="Reserve asset" %}
Any asset whose liquidity is actively maintained by Router Protocol falls under the category of reserve assets. Users will be allowed to stake these assets on Router's bridge contract in exchange for attractive yields. Reserve assets are further classified into two categories:

* **Non-stable reserve assets:** MATIC, BNB, AVAX, FTM, ETH, ONE, CRO
* **Stable reserve assets:** USDC
{% endtab %}

{% tab title="Mintable asset" %}
Any asset whose minting privilege lies with Router's bridge contract comes under this category. E.g., ROUTE, DFYN, etc.
{% endtab %}

{% tab title="Arbitrary asset" %}
Any asset which does not fall under any of the other two categories is termed as an arbitrary asset. E.g., SHIB, CRV, LINK, AAVE, etc.
{% endtab %}
{% endtabs %}

### Scenario 1: Transferring stable reserve assets

In a stable reserve asset transfer, your stable asset will be locked on the source chain and unlocked on the destination chain. If the bridge does not have sufficient liquidity of that asset on the destination chain, you will receive a wrapped version of that asset (RUSDC in case of USDC).

### Scenario 2: Transferring non-stable reserve assets

Say you want to transfer a non-stable reserve asset, MATIC, from chain A to chain B. This transaction can be completed in one of the following two ways:

**Path 1 -** Your MATIC tokens will be locked on chain A and an equivalent amount of MATIC will be unlocked on chain B.&#x20;

**Path 2 -** Your MATIC tokens will be converted to a stable reserve asset (USDC), which will be locked on chain A. An equivalent amount of USDC will then be unlocked on chain B to buy MATIC tokens and send them to your wallet.

{% hint style="info" %}
Among these two, the pathfinder will choose the path which gives the most optimal solution, i.e., most number of MATIC tokens on the target chain.&#x20;
{% endhint %}

### Scenario 3: Transferring mintable assets

Say you want to transfer 5 ROUTE tokens from chain A to chain B. 5 ROUTE will be locked on chain A, following which 5 ROUTE will be minted on chain B. Now while transferring ROUTE back from chain B to chain A, ROUTE tokens will be burnt on chain B and unlocked on chain A.&#x20;

{% hint style="info" %}
These mintable assets will be locked/unlocked on the chain where they were originally launched and minted/burnt on all the other chains.&#x20;
{% endhint %}

### Scenario 4: Transferring/swapping arbitrary assets

Arbitrary asset transfers and swaps can be categorized together since they follow the same transaction flow. Let us consider a scenario wherein a user wants to swap an arbitrary asset, SHIB, on chain A with another arbitrary asset, LINK, on chain B.

**Step 1)** SHIB will be converted to a stable reserve asset (USDC) on chain A.&#x20;

**Step 2)** USDC will be locked on chain A.

**Step 3)** An equivalent amount of USDC will be unlocked on chain B.

**Step 4)** The unlocked USDC tokens will be used to buy LINK using a DEX on the destination&#x20;

chain.

{% hint style="info" %}
In the case of a transfer, the unlocked USDC would have been used to buy SHIB tokens on the destination chain.
{% endhint %}

### Scenario 5: Swapping between two reserve assets

Say you want to swap a reserve asset X on chain A for a reserve asset Y on chain B. The paths possible in such a scenario are given below:

**Path 1 -** Your X tokens will be locked on chain A and an equivalent amount of X tokens will be unlocked on chain B. These unlocked tokens will then be used to buy Y tokens.

**Path 2 -** Your X tokens will be swapped for Y tokens and locked on chain A. On chain B, an equivalent amount of Y tokens will be unlocked and credited to your destination wallet address.

In addition to the aforementioned paths, another path is possible while swapping between two non-stable reserve assets:

**Path 3 -** Your X tokens will be converted to a stable reserve asset and locked on chain A. An equivalent amount of the same stable reserve asset will be unlocked on chain B and used to buy token Y.

{% hint style="info" %}
Even in the case of stable reserve assets, the token X on chain A --> token Y on chain B can happen through another stable asset Z.&#x20;
{% endhint %}

### Scenario 6: Swapping between two mintable assets or between one mintable & one arbitrary asset

Swaps under this scenario will have the same flow as that in [Scenario 4](transfer-flows.md#scenario-4-transferring-swapping-arbitrary-assets), i.e., these swaps will also take place via stable reserve assets.

### Scenario 7: Swapping between one reserve and one mintable/arbitrary asset

Consider a case in which a user wants to swap MATIC tokens on chain A with ROUTE on chain B. Such a swap can have the following paths:

**Path 1 -** User's MATIC tokens will be converted to a stable reserve asset (USDC) and locked on chain A. An equivalent amount of USDC will be unlocked on chain B and converted to ROUTE.

**Path 2 -** User's MATIC tokens will be locked on chain A and an equivalent amount of MATIC tokens will be unlocked on chain B. Following this, the unlocked MATIC tokens will be used to buy ROUTE tokens from a DEX on the destination chain.

**Path 3 -** User's MATIC tokens will be converted to ROUTE on chain A and an equivalent amount of ROUTE will be minted on chain B.

{% hint style="info" %}
A non-stable reserve asset or a mintable asset can only be used as a medium of value transfer in transactions where the source or the destination token is that specific asset. E.g., MATIC can only be used as a medium of value transfer if the user deposits MATIC on the source chain or desires MATIC on the destination chain. &#x20;
{% endhint %}
