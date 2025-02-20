# NFT

The NFT (Non-Fungible Token) module in Me-Hub manages the creation, transfer, and querying of NFTs. This module is built on top of the Cosmos SDK and provides a robust framework for handling NFTs within the blockchain application.

## Key Components

- **NFTKeeper**: The keeper responsible for managing NFTs.
- **StoreKey**: The key used to access the NFT store.
- **AccountKeeper**: Manages accounts and their permissions.
- **BankKeeper**: Manages token balances and transfers.

## Initialization

The NFT module is initialized in the `AppKeepers` struct. Below is the initialization code:

```go
a.WNFTKeeper = wnftkeeper.NewKeeper(
    appCodec,
    a.keys[nftkeeper.StoreKey],
    a.AccountKeeper,
    a.BankKeeper,
)
```

# Features

- Minting: Create new NFTs and assign them to accounts.
- Transfer: Transfer NFTs between accounts.
- Querying: Query NFTs by owner, ID, and other attributes.


#SBT