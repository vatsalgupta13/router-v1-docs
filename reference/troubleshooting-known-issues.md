# Troubleshooting Known Issues

<details>

<summary>Issue 1: Transaction tracker graphic disappeared on its own</summary>

In some cases, the transaction tracker (train-like graphic) shown on the Router UI might suddenly disappear during the transaction. This happens due to issues with the WebSocket connection that fetches the transaction events. However, there is nothing to be worried about, your transaction will still continue in the background and will provide you with the relevant asset on the destination chain. You can use your address on the relevant blockchain explorer to check if you received the funds in your wallet.&#x20;

</details>

<details>

<summary>Issue 2: “Fail with error 'OneSplit: actual return amount is less than minReturn'” </summary>

In rare cases, a cross-chain transaction on Router might get reverted with this error on the source side ("Contract Interaction Failed") or you might see this error on the UI. This means that the slippage tolerance was breached on the source side while converting your asset to a stablecoin.&#x20;

#### **How to resolve this issue?**

After increasing the slippage tolerance from the settings, your transaction should go through.

</details>

<details>

<summary>Issue 3: “Execution reverted: ERC20: call failed”</summary>

If you receive this error while trying a cross-chain transaction, it could mean one of two things - either (a) there is some issue with the token approval or (b) you do not have sufficient funds in your wallet to pay for the transaction fees.&#x20;

#### How to resolve this issue?&#x20;

* Try doing a hard refresh
  * `Cmd + Shift + R` on Mac
  * `Ctrl + F5` on Windows
* Check if you have enough tokens to pay the transaction fees. If not, add more tokens to your wallet or select a different fee token.

</details>

<details>

<summary>Issue 4: My funds were locked on the source chain but I haven't them on the target chain side even after waiting for a long time</summary>

This issue is likely to occur when you try to swap into a token that has a non-standard ERC20 implementation (these tokens often have limited transfer capabilities). In such cases, you might lose your funds permanently so we highly recommend that you do not swap non-standard ERC20 tokens on Router Protocol.

</details>
