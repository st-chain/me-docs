# IBC(Inter-Blockchain Communication)

The IBC module provides Inter-Blockchain Communication (IBC) functionalities within the ME-HUB application. It includes the `IBCKeeper` which is responsible for managing IBC operations.

Key components:
- `IBCKeeper`: Manages IBC operations.
- `TransferKeeper`: Manages IBC token transfers.

Initialization:
```go
a.IBCKeeper = ibckeeper.NewKeeper(
    appCodec,
    a.keys[ibcexported.StoreKey],
    a.GetSubspace(ibcexported.ModuleName),
    a.StakingKeeper,
    a.UpgradeKeeper,
    a.ScopedIBCKeeper,
)

a.TransferKeeper = ibctransferkeeper.NewKeeper(
    appCodec,
    a.keys[ibctransfertypes.StoreKey],
    a.GetSubspace(ibctransfertypes.ModuleName),
    denommetadatamodule.NewICS4Wrapper(a.IBCKeeper.ChannelKeeper, a.RollappKeeper, a.BankKeeper),
    a.IBCKeeper.ChannelKeeper,
    &a.IBCKeeper.PortKeeper,
    a.AccountKeeper,
    a.BankKeeper,
    a.ScopedTransferKeeper,
)
```