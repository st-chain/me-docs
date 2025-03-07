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

### Using Commands in the WNFT Module for Sending Transactions

The WNFT module provides several commands to manage NFTs (Non-Fungible Tokens). These commands can be used to create new classes, mint NFTs, and send NFTs. The WNFT module is compatible with the Cosmos SDK's NFT module.

#### Commands

1. **Create New Class**
    - **Command**: `new-class [class-id] [name] [symbol] [description] [uri] [uri_hash] [total_supply]`
    - **Description**: Creates a new NFT class.
    - **Example**:
      ```sh
      med tx wnft new-class class1 "Class Name" "SYM" "Description" "http://example.com" "hash" 100 --from me1...
      ```

2. **Mint NFT**
    - **Command**: `mint [class-id] [token-id] [uri] [uri-hash]`
    - **Description**: Mints a new NFT.
    - **Example**:
      ```sh
      med tx wnft mint class1 token1 "http://example.com" "hash" --from me1...
      ```

3. **Send NFT**
    - **Command**: `send [class-id] [token-id] [recipient]`
    - **Description**: Sends an NFT to a recipient.
    - **Example**:
      ```sh
      med tx nft send class1 token1 me1recipient --from me1...
      ```

### Using Commands in the WNFT and Reference NFT Module for Querying

The WNFT and Reference NFT modules provide several commands to query information about NFTs (Non-Fungible Tokens). These commands can be used to retrieve details about NFT classes, individual NFTs, and their owners.

#### Commands

1. **Query NFT Class**
    - **Command**: `class [class-id]`
    - **Description**: Queries the details of an NFT class with the specified class ID.
    - **Example**:
      ```sh
      med query wnft class class1
      ```

2. **Query All NFT Classes**
    - **Command**: `classes`
    - **Description**: Queries the list of all NFT classes.
    - **Example**:
      ```sh
      med query wnft classes
      ```

3. **Query NFT**
    - **Command**: `nft [class-id] [token-id]`
    - **Description**: Queries the details of an NFT with the specified class ID and token ID.
    - **Example**:
      ```sh
      med query wnft nft class1 token1
      ```

4. **Query All NFTs**
    - **Command**: `nfts [class-id]`
    - **Description**: Queries the list of all NFTs in the specified class.
    - **Example**:
      ```sh
      med query wnft nfts class1
      ```

5. **Query NFT Owner**
    - **Command**: `owner [class-id] [token-id]`
    - **Description**: Queries the owner of an NFT with the specified class ID and token ID.
    - **Example**:
      ```sh
      med query wnft owner class1 token1
      ```

6. **Query NFT Balance**
    - **Command**: `balance [owner]`
    - **Description**: Queries the balance of NFTs owned by the specified address.
    - **Example**:
      ```sh
      med query wnft balance me1...
      ```

7. **Query NFT Supply**
    - **Command**: `supply [class-id]`
    - **Description**: Queries the total supply of NFTs in the specified class.
    - **Example**:
      ```sh
      med query wnft supply class1
      ```

8. **Query Class Address**
    - **Command**: `class-address [class-id] [owner]`
    - **Description**: Queries information and status related to the specified NFT class and owner.
    - **Example**:
      ```sh
      med query wnft class-address class1 me1...
      ```

9. **Query NFT Filter**
    - **Command**: `nft-filter --class-id [class-id] --token-id [token-id] --owner [owner]`
    - **Description**: Queries NFTs based on the specified filters.
    - **Example**:
      ```sh
      med query wnft nft-filter --class-id class1 --token-id token1 --owner me1...
      ```
