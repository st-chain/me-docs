# KYC(Know Your Customer)

## Using Commands in the KYC Module for tx

The KYC module provides several commands to manage KYC (Know Your Customer) information. These commands can be used to approve, update, remove KYC information, and manage Soul Binding Tokens (SBTs).

#### Commands

1. **Approve KYC Information**
    - **Command**: `approve [DID] [region ID] [address] [pubkey] [level] [uri] [hash] [inviter address]`
    - **Description**: Approves KYC information for a given DID.
    - **Example**:
      ```sh
       tx kyc approve did:example:123 1 me1... pubkey 2 http://example.com hash me1...
      ```

2. **Update KYC Information**
    - **Command**: `update [DID] [region ID] [level] [uri] [hash]`
    - **Description**: Updates KYC information for a given DID.
    - **Example**:
      ```sh
      med tx kyc update did:example:123 1 2 http://example.com hash
      ```

3. **Remove KYC Information**
    - **Command**: `remove [DID]`
    - **Description**: Removes KYC information for a given DID.
    - **Example**:
      ```sh
      med tx kyc remove did:example:123
      ```

4. **Create SBT (Soul Binding Token)**
    - **Command**: `create-sbt [DID] [uri] [uri hash] [data]`
    - **Description**: Creates a new SBT for a given DID.
    - **Example**:
      ```sh
      med tx kyc create-sbt did:example:123 http://example.com hash 0x1234
      ```

5. **Update SBT**
    - **Command**: `update-sbt [DID] [uri] [uri hash] [data]`
    - **Description**: Updates an existing SBT for a given DID.
    - **Example**:
      ```sh
      med tx kyc update-sbt did:example:123 http://example.com hash 0x1234
      ```

6. **Delete SBT**
    - **Command**: `delete-sbt [DID]`
    - **Description**: Deletes an existing SBT for a given DID.
    - **Example**:
      ```sh
      med tx kyc delete-sbt did:example:123
      ```

#### Flags

- `--home`: The application home directory.
- `--keyring-backend`: Select keyring's backend (os|file|test).
- `--chain-id`: The chain ID of the network.
- `--node`: The node to connect to.

## Using Commands in the KYC Module for Querying

The KYC module provides several commands to query KYC (Know Your Customer) information. These commands can be used to retrieve protocol details, DID information, KYC information, and Soul Binding Tokens (SBTs).

#### Commands

1. **Query KYC Protocol**
   - **Command**: `protocol`
   - **Description**: Shows the KYC protocol.
   - **Example**:
     ```sh
     med query kyc protocol
     ```

2. **Query DID**
   - **Command**: `did [address]`
   - **Description**: Queries the DID information for a given address.
   - **Example**:
     ```sh
     med query kyc did me1...
     ```

3. **Query KYC Information**
   - **Command**: `kyc [DID]`
   - **Description**: Queries the KYC information for a given DID.
   - **Example**:
     ```sh
     med query kyc kyc did:example:123
     ```

4. **Query All KYCs**
   - **Command**: `KYCs`
   - **Description**: Queries all KYC information, optionally filtered by region.
   - **Example**:
     ```sh
     med query kyc KYCs --region me_earth
     ```

5. **Query SBT Information**
   - **Command**: `sbt [did]`
   - **Description**: Queries the SBT information for a given DID.
   - **Example**:
     ```sh
     med query kyc sbt did:example:123
     ```

#### Flags

- `--home`: The application home directory.
- `--keyring-backend`: Select keyring's backend (os|file|test).
- `--chain-id`: The chain ID of the network.
- `--node`: The node to connect to.
- `--region`: Filter by region ID (used with `KYCs` command).
- `--page`: Page number for pagination (used with `KYCs` command).
- `--limit`: Number of results per page (used with `KYCs` command).
