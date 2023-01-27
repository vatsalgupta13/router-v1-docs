# Proxy Contract Implementation

A proxy architecture involves the deployment of two contracts:

1. **Logic/Implementation Contract** - This contract implements the actual protocol logic that users want to interact with.
2. **Proxy contract** - This contract is responsible for listening to users’ message calls and redirecting them to the latest deployed logic contract.

![Schematic View of Proxy Contract Architecture](<../../../.gitbook/assets/Proxy Contract Implementation.png>)

By employing a dedicated proxy architecture, Router retains the option to update the contract in case of any contract vulnerability/bug. It also makes it possible for Router to add new handler contracts to the system without disturbing the existing state. If at any time in the future, Router needs to upgrade the existing implementation, a new version of the logic contract can be deployed, and the proxy can be updated to reference the new logic contract address.

{% hint style="info" %}
The change in the implementation contract will not affect your funds/balances since it’s the proxy contract that maintains the state and not the implementation contract.
{% endhint %}

Router follows OpenZeppelin’s latest proxy standard, [EIP-1822: Universal Upgradeable Proxy Standard (UUPS)](https://eips.ethereum.org/EIPS/eip-1822#motivation), in its implementation of the proxy architecture. UUPS improves upon the existing proxy implementations by (a) making it easier for the developers to deploy and maintain the proxy and logic contracts and (b) facilitating greater transparency by standardizing the methods for verifying the bytecode used by the proxy contract.
