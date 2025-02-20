# EVM Module

The EVM module provides Ethereum Virtual Machine (EVM) compatibility within the ME-HUB application. It includes the `EvmKeeper` which is responsible for managing EVM operations.

Key components:
- `EvmKeeper`: Manages EVM operations.
- `FeeMarketKeeper`: Manages the fee market for EVM transactions.

Initialization:
```go
a.EvmKeeper = evmkeeper.NewKeeper(
    ethermintevmkeeper.NewKeeper(
        appCodec,
        a.keys[evmtypes.StoreKey],
        a.tkeys[evmtypes.TransientKey],
        authtypes.NewModuleAddress(govtypes.ModuleName),
        a.AccountKeeper,
        a.BankKeeper,
        a.StakingKeeper,
        a.FeeMarketKeeper,
        nil,
        geth.NewEVM,
        tracer,
        a.GetSubspace(evmtypes.ModuleName),
    ))
```
