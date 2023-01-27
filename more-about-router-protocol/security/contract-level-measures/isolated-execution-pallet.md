# Isolated Execution Pallet

Router features an isolated execution pallet into which other smart contract execution engines can be embedded. This pallet provides a dedicated smart contract compiler, interpreter, executor, and other related components for other developers to run their code on. Since the pallet executes the calldata on a stateless handler contract, the function calls are completely tamper-proof. This ensures that no malicious code can drain data from the original bridge contract reserve.
