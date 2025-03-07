### Fee Deduction and Allocation Process

The `DeductFeeDecorator` is responsible for deducting transaction fees from the first signer of the transaction. If the first signer does not have sufficient funds to cover the fees, an `InsufficientFunds` error is returned. If the fees are successfully deducted, the next `AnteHandler` in the chain is called.

1. **Fee Deduction**:
    - The decorator checks if the transaction implements the `FeeTx` interface.
    - It verifies that the gas limit is positive if the transaction is not a simulation and the block height is greater than zero.
    - The decorator retrieves the fee payer and fee granter from the transaction.
    - If the fee granter is set and different from the fee payer, the decorator attempts to use the granted fees.
    - It checks if the fee payer has sufficient funds to cover the transaction fees.
    - If the fee payer has enough funds, the fees are deducted from their account.

2. **Fee Allocation**:
    - The deducted fees are split into different portions based on predefined rates (10%, 20%, 30%, and 40%).
    - The 10% portion is allocated to the development operator.
    - The 20% portion is allocated to either the KYC region owner or the proposer owner, depending on the fee payer's KYC status.
    - The remaining 70% (30% + 40%) is allocated to the global DAO fee pool or the contract creator if the transaction involves a WASM contract.

3. **Event Emission**:
    - An event is emitted to record the fee deduction and allocation process.

This process ensures that transaction fees are properly deducted and allocated to the appropriate recipients, maintaining the integrity and sustainability of the network.