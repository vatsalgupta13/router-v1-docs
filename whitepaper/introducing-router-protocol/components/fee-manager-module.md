# Fee Manager Module

With Router, users will have the utmost flexibility in choosing which token to use for transaction fees. Users can choose between:

* Native gas token on the source chain (default)
* USDC
* ROUTE (50% concession in transaction fees)
* DFYN (20% concession in transaction fees)

Router Protocol uses a fee manager module that estimates the transaction fees every 30-60 minutes depending on the congestion on different networks. This fee manager module is entirely modular and can support tokens other than the ones mentioned above, giving users even more flexibility. Since Router's fee manager module is not tightly coupled with the rest of the code, other projects are welcome to use it.
