# FAQs

<details>

<summary>Q) Which chains does Router support right now?</summary>

Ans) Router currently supports cross-chain transactions between ten networks - Ethereum, Polygon, BSC, Avalanche, Fantom, Harmony, Arbitrum, Optimism, Cronos, and Aurora.

</details>

<details>

<summary>Q) Can I expect some slippage during a cross-chain swap?</summary>

Ans) Router enables cross-chain swaps by accessing DEXes on both sides of the chain. Although Router uses stablecoins as the medium of value transfer to minimize the impact of price volatility faced by the end-user, there is always a risk of price change on DEXes, which can result in some slippage. Note that, you won't face any slippage while transferring any reserve/mintable assets.

</details>

<details>

<summary>Q) Which wallets are supported by Router?</summary>

Router supports all the major wallets including MetaMask, FortMatic, Torus, Portis, Bitski. Apart from these wallets, you can use Router with any wallet compatible with WalletConnect.

</details>

<details>

<summary>Q)  Whenever I choose the native (gas) token as the bridge fee token, why does my source chain's block explorer show me multiple transactions before my deposit transaction?</summary>

Ans) Router uses only ERC-20 tokens while deducting the fees. Hence, when you choose the native gas token as your fee token, the deduction of fees gets broken down into three transactions:

1. Native tokens equal to the transaction fee amount are debited from your wallet;
2. Native token is converted into its wrapped version, which is deposited into your wallet;&#x20;
3. This wrapped version of the native asset is withdrawn from your wallet;&#x20;

Let's say the transaction fee is 2 MATIC --> your MATIC tokens will be converted to WMATIC --> 2 WMATIC will be credited to your wallet --> 2 WMATIC will be withdrawn from your wallet as a transaction fee. The net amount deducted from your wallet account remains 2 MATIC.

</details>

<details>

<summary>Q) How can I swap or transfer a token that is not a part of Router's default list?</summary>

Ans) With Router, you can transfer/swap any token across chains. To transfer/swap a token that is not present in Router's default token list, follow the steps given below:

1. Find the address of the token you wish to transfer/receive and copy it; Note - the token's address will be different on different chains, so please find the address on the correct chain.
2. Click on the source/destination token dropdown.
3. In the search option, paste the address of the token you had copied earlier.
4. You will then see an option to import that token.
5. Once the token is successfully imported, you will be able to transfer/receive that token.

</details>

<details>

<summary>Q) I got a wrapped asset from the bridge; why did that happen, and what should I do with it?</summary>

Ans) In a scenario where the liquidity of the reserve asset (MATIC, BNB, or USDC) on the destination side gets depleted while your transaction is being processed, you might end up getting R-Asset (e.g., RMATIC, RBNB, RUSDC). To redeem the R-Asset for its original version, you can check out the guide given [here](../how-to/redeem-r-asset-for-asset.md).&#x20;

</details>

<details>

<summary>Q) I selected $ASSET (e.g., $SHIB, $CRV, etc.) on the destination chain, but I ended up getting USDC; why did that happen?</summary>

Ans) Before diving into why this happened, let us understand the steps involved in an arbitrary cross-chain token transaction on Router:

1. Router uses a DEX on the source chain to convert your token to stablecoin.
2. The stablecoins are locked on the source chain.
3. An equivalent amount of stablecoins are unlocked on the destination chain.
4. The unlocked stablecoins are converted to the desired token on the destination chain.

During the 4th leg of this transaction, there is a chance that the transaction slippage is higher than the accepted slippage while initiating the transaction. In this case, the final leg of this transaction fails, and you are given a stablecoin such as USDC.

</details>

<details>

<summary>Q) It has been quite some time since I initiated my transaction. The transaction tracker graphic seems stuck. How can I check the status of my transaction?</summary>

Ans) In case your transaction is stuck for a long time and the transaction tracker is not moving, you can check whether you have received funds on the destination side by checking [Router's cross-chain explorer](https://explorer.routerprotocol.com/).&#x20;

</details>
