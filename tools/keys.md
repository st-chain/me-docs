### Using the `keys` Command

The `keys` command in the Evmos Ethermint library allows you to manage your application's keys. These keys can be used by light-clients, full nodes, or any other application that needs to sign with a private key. The keyring supports various backends for storing keys securely.

#### Keyring Backends

The keyring supports the following backends:
- **os**: Uses the operating system's default credentials store.
- **file**: Uses an encrypted file-based keystore within the app's configuration directory. This keyring will request a password each time it is accessed.
- **kwallet**: Uses KDE Wallet Manager as a credentials management application.
- **pass**: Uses the `pass` command line utility to store and retrieve keys.
- **test**: Stores keys insecurely to disk. It does not prompt for a password to be unlocked and should be used only for testing purposes.

#### Commands

Here are the available commands under `keys`:

- **add**: Add a new key to the keyring.
- **mnemonic**: Generate a new mnemonic key.
- **export**: Export a key from the keyring.
- **import**: Import a key into the keyring.
- **import-hex**: Import a key from a hex string.
- **list**: List all keys in the keyring.
- **show**: Show details of a specific key.
- **delete**: Delete a key from the keyring.
- **rename**: Rename a key in the keyring.
- **parse**: Parse a key string.
- **migrate**: Migrate keys to a new format.
- **unsafe-export-eth**: Export an Ethereum key (unsafe).
- **unsafe-import**: Import a key (unsafe).

#### Usage Examples

1. **Add a New Key**:
   ```sh
   med keys add mykey
   ```

2. **List All Keys**:
   ```sh
   med keys list
   ```

3. **Show Key Details**:
   ```sh
   med keys show mykey
   ```

4. **Export a Key**:
   ```sh
   med keys export mykey
   ```

5. **Import a Key**:
   ```sh
   med keys import mykey
   ```

6. **Delete a Key**:
   ```sh
   med keys delete mykey
   ```
