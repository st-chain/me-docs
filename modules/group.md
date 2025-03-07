# Group

### Using Commands in the MEGroup Module for Sending Transactions

The MEGroup module provides several commands to manage groups. These commands can be used to create, join, and leave groups.

#### Commands

1. **Create Group**
    - **Command**: `create-group [name] [description]`
    - **Description**: Creates a new group.
    - **Example**:
      ```sh
      med tx megroup create-group "Group Name" "Group Description"
      ```

2. **Join Group**
    - **Command**: `join-group [group-id] [address]`
    - **Description**: Joins a group with the specified group ID.
    - **Example**:
      ```sh
      med tx megroup join-group 1 me1...
      ```

3. **Leave Group**
    - **Command**: `leave-group [group-id] [address]`
    - **Description**: Leaves a group with the specified group ID.
    - **Example**:
      ```sh
      med tx megroup leave-group 1 me1...
      ```

### Using Commands in the MEGroup Module for Querying

The MEGroup module provides several commands to query group-related information. These commands can be used to retrieve details about groups and their members.

#### Commands

1. **Query Group**
   - **Command**: `group [group-id]`
   - **Description**: Queries the details of a group with the specified group ID.
   - **Example**:
     ```sh
     med query megroup group 1
     ```

2. **Query Group Members**
   - **Command**: `group-members [group-id]`
   - **Description**: Queries the members of a group with the specified group ID.
   - **Example**:
     ```sh
     med query megroup group-members 1
     ```

3. **Query All Groups**
   - **Command**: `all-groups`
   - **Description**: Queries the list of all groups.
   - **Example**:
     ```sh
     med query megroup all-groups
     ```
