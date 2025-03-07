# DID(Decentralized Identifier)

### Using Commands in the DID Module for Sending Transactions

The DID module provides several commands to manage Decentralized Identifiers (DIDs) and related services. These commands can be used to create, update, and remove DIDs, services, and verifiable credentials (VCs).

#### Commands

1. **Create DID**
    - **Command**: `create-did [did] [public-key-for-address]`
    - **Description**: Creates a new DID.
    - **Example**:
      ```sh
      med tx did create-did did:example:123 publickey
      ```

2. **Update DID Status**
    - **Command**: `update-did-status [did] [status]`
    - **Description**: Updates the status of a DID. Status: 1-active, 0-inactive.
    - **Example**:
      ```sh
      med tx did update-did-status did:example:123 1
      ```

3. **Create Service**
    - **Command**: `create-service [sid] [name] [description] [issuer]`
    - **Description**: Creates a new credential service.
    - **Example**:
      ```sh
      med tx did create-service service1 "Service Name" "Service Description" me1...
      ```

4. **Update Service Status**
    - **Command**: `update-service-status [sid] [status]`
    - **Description**: Updates the status of a credential service. Status: 1-active, 0-inactive.
    - **Example**:
      ```sh
      med tx did update-service-status service1 1
      ```

5. **Create Verifiable Credential (VC)**
    - **Command**: `create-vc [holder-did] [sid] [credential-file-hash] [off-chain-credential-uri] [hex-data]`
    - **Description**: Creates a new verifiable credential.
    - **Example**:
      ```sh
      med tx did create-vc did:example:123 service1 hash http://example.com 0x1234
      ```

6. **Update Verifiable Credential (VC)**
    - **Command**: `update-vc [holder-did] [sid] [credential-file-hash] [off-chain-credential-uri] [hex-data]`
    - **Description**: Updates an existing verifiable credential.
    - **Example**:
      ```sh
      med tx did update-vc did:example:123 service1 hash http://example.com 0x1234
      ```

7. **Remove Verifiable Credential (VC)**
    - **Command**: `remove-vc [holder] [sid]`
    - **Description**: Removes an existing verifiable credential.
    - **Example**:
      ```sh
      med tx did remove-vc did:example:123 service1
      ```
### Using Commands in the DID Module for Querying

The DID module provides several commands to query Decentralized Identifiers (DIDs) and related services. These commands can be used to retrieve DID information, DID documents, services, and verifiable credentials (VCs).

#### Commands

1. **Query DID**
   - **Command**: `did [address]`
   - **Description**: Queries the DID information for a given address.
   - **Example**:
     ```sh
     med query did did me1...
     ```

2. **Query DID Document**
   - **Command**: `document [did]`
   - **Description**: Queries the DID document for a given DID.
   - **Example**:
     ```sh
     med query did document did:example:123
     ```

3. **Query Service**
   - **Command**: `service [sid]`
   - **Description**: Queries the credential service for a given service ID.
   - **Example**:
     ```sh
     med query did service service1
     ```

4. **Query Verifiable Credential (VC)**
   - **Command**: `credential [did] [sid]`
   - **Description**: Queries the verifiable credential for a given DID and service ID.
   - **Example**:
     ```sh
     med query did credential did:example:123 service1
     ```

5. **Query DID Infos**
   - **Command**: `did-infos`
   - **Description**: Queries the list of base information for all DIDs.
   - **Example**:
     ```sh
     med query did did-infos
     ```
     