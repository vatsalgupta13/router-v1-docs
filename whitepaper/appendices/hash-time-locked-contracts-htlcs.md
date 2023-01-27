# Hash Time-locked Contracts (HTLCs)

One of the earliest models developed to enable cross-chain operations was Hash Time-locked Contracts (HTLCs), which employs hash locks [\[10\]](../references.md#10-hashlock.-https-en.bitcoin.it-wiki-hashlock-2015.) and timelocks [\[11\]](../references.md#11-timelock.-https-en.bitcoin.it-wiki-timelock-2016.) to ensure that the operations remain atomic. Even though HTLC implementations differ across projects, the overall concept remains the same [\[12\]](../references.md#12-rafael-belchior-andr-e-vasconcelos-s-ergio-guerreiro-and-miguel-correia.-a-survey-on-blockchain-i).&#x20;

### How do HTLCs work?

To understand how HTLCs enable cross-chain swaps, consider the following scenario: Alice has a token X on Chain A and wishes to trade it with Bob, who has token Y on Chain B.&#x20;

**Step 1)** Alice hashes a secret code to obtain hash lock h1. Alice also generates a timelock t1 corresponding to an upper bound in which the hash lock can be unlocked.&#x20;

**Step 2)** Alice uses these locks to create a smart contract $$c_{a}$$ on chain A and locks her funds in that contract.&#x20;

**Step 3)** Bob acknowledges that Alice has locked her funds.&#x20;

**Step 4)** Bob uses the same hash lock h1 and a different timelock t2 to create a contract $$c_{b}$$ on chain B. To ensure that Bob gets adequate time to claim funds from contract $$c_{a}$$, t2 will be less than t1.&#x20;

**Step 5)** Alice unlocks Bob’s funds from contract $$c_{b}$$, thereby revealing the secret code.&#x20;

**Step 6)** Bob uses the revealed secret to unlock Alice’s funds from contract $$c_{a}$$ on chain A.&#x20;

**Step 7)** If the swap does not go through, Alice and Bob can claim their funds back once the timelock on the individual contracts expires.&#x20;

### Drawbacks

One upside of using HTLC techniques is that they do not introduce any trust assumptions. However, they suffer from a range of issues that limits their efficacy.&#x20;

* They require all the concerned parties to always be online. Both the sender and the receiver need to monitor the involved blockchains during execution actively.
* They are very slow and inefficient since every cross-chain swap requires a total of four transactions (two on each blockchain) [\[13\]](../references.md#13-alexei-zamyatin-dominik-harz-joshua-lind-panayiotis-panayiotou-arthur-gervais-and-william-knotten).
* Given the high fees and waiting periods involved with HTLC-based swaps, the scalability of this approach is also a concern.
