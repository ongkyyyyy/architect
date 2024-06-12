## SOFTWARE DOCUMENTATION

Database Structure and Relationships
Tables and Their Structures

1. accesses
    Description: Stores information about different accesses available in the system.

    Table Structure:
    access_id (bigint UNSIGNED, PRIMARY KEY, AUTO_INCREMENT): Unique identifier for each access.
    access_name (varchar(255)): Name of the access.
    access_description (varchar(255), NULLABLE): Description of the access.
    created_at (timestamp, NULLABLE): Timestamp indicating when the access was created.
    updated_at (timestamp, NULLABLE): Timestamp indicating when the access was last updated.

2. access_roles
    Description: Maps accesses to roles within the system.

    Table Structure:
    access_role_id (bigint UNSIGNED, PRIMARY KEY, AUTO_INCREMENT): Unique identifier for each access-role mapping.
    access_id (bigint UNSIGNED): Foreign key referencing accesses(access_id).
    role_id (bigint UNSIGNED): Foreign key referencing roles(role_id).
    created_at (timestamp, NULLABLE): Timestamp indicating when the access-role mapping was created.
    updated_at (timestamp, NULLABLE): Timestamp indicating when the access-role mapping was last updated.

    Relationships:
    access_id references accesses(access_id) on DELETE CASCADE and UPDATE CASCADE.
    role_id references roles(role_id) on DELETE CASCADE and UPDATE CASCADE.

3. logs
    Description: Records actions performed by users in the system.

    Table Structure:
    log_id (bigint UNSIGNED, PRIMARY KEY, AUTO_INCREMENT): Unique identifier for each log entry.
    users_id (bigint UNSIGNED): Foreign key referencing users(users_id).
    action (varchar(255)): Description of the action performed.
    created_at (timestamp, NULLABLE): Timestamp indicating when the log entry was created.
    updated_at (timestamp, NULLABLE): Timestamp indicating when the log entry was last updated.

    Relationships:
    users_id references users(users_id) on DELETE CASCADE.

4. permissions
    Description: Stores information about different permissions available in the system.

    Table Structure:
    permission_id (bigint UNSIGNED, PRIMARY KEY, AUTO_INCREMENT): Unique identifier for each permission.
    permission_name (varchar(255)): Name of the permission.
    permission_description (varchar(255), NULLABLE): Description of the permission.
    created_at (timestamp, NULLABLE): Timestamp indicating when the permission was created.
    updated_at (timestamp, NULLABLE): Timestamp indicating when the permission was last updated.

5. personal_identities
    Description: Stores personal identity information of users.

    Table Structure:
    personal_identity_id (bigint UNSIGNED, PRIMARY KEY, AUTO_INCREMENT): Unique identifier for each personal identity.
    users_id (bigint UNSIGNED): Foreign key referencing users(users_id).
    Various other fields storing personal identity information (varchar(255), NULLABLE).
    created_at (timestamp, NULLABLE): Timestamp indicating when the personal identity was created.
    updated_at (timestamp, NULLABLE): Timestamp indicating when the personal identity was last updated.

6. roles
    Description: Stores information about different roles available in the system.

    Table Structure:
    role_id (bigint UNSIGNED, PRIMARY KEY, AUTO_INCREMENT): Unique identifier for each role.
    role_name (varchar(255)): Name of the role.
    role_description (varchar(255), NULLABLE): Description of the role.
    created_at (timestamp, NULLABLE): Timestamp indicating when the role was created.
    updated_at (timestamp, NULLABLE): Timestamp indicating when the role was last updated.

7. role_permissions
    Description: Maps roles to permissions within the system.

    Table Structure:
    role_permission_id (bigint UNSIGNED, PRIMARY KEY, AUTO_INCREMENT): Unique identifier for each role-permission mapping.
    role_id (bigint UNSIGNED): Foreign key referencing roles(role_id).
    permission_id (bigint UNSIGNED): Foreign key referencing permissions(permission_id).
    created_at (timestamp, NULLABLE): Timestamp indicating when the role-permission mapping was created.
    updated_at (timestamp, NULLABLE): Timestamp indicating when the role-permission mapping was last updated.

    Relationships:
    role_id references roles(role_id) on DELETE CASCADE and UPDATE CASCADE.
    permission_id references permissions(permission_id) on DELETE CASCADE and UPDATE CASCADE.

8. sessions
    Description: Stores session data for users.

    Table Structure:
    id (varchar(255), PRIMARY KEY): Session ID.
    user_id (bigint UNSIGNED, NULLABLE): Foreign key referencing users(users_id).
    ip_address (varchar(45), NULLABLE): IP address of the user.
    user_agent (text, NULLABLE): User agent string.
    payload (longtext): Session data.
    last_activity (int): Timestamp of the last activity.

9. users
    Description: Stores information about users.

    Table Structure:
    users_id (bigint UNSIGNED, PRIMARY KEY, AUTO_INCREMENT): Unique identifier for each user.
    name (varchar(255)): Name of the user.
    email (varchar(255), UNIQUE): Email address of the user.
    email_verified_at (timestamp, NULLABLE): Timestamp indicating when the email was verified.
    username (varchar(255), UNIQUE, NULLABLE): Username of the user.
    password (varchar(255)): Hashed password.
    primary_phone (varchar(255), UNIQUE, NULLABLE): Primary phone number.
    avatar (varchar(255), NULLABLE): URL of the avatar image.
    application_id (varchar(255), NULLABLE): Application ID.
    custom_data (longtext, NULLABLE): Custom data in JSON format.
    identities (longtext, NULLABLE): Identities in JSON format.
    last_sign_in_at (timestamp, NULLABLE): Timestamp of the last sign-in.
    is_suspended (tinyint, DEFAULT 1): Suspension status.
    remember_token (varchar(100), NULLABLE): Remember token.
    created_at (timestamp, NULLABLE): Timestamp indicating when the user was created.
    updated_at (timestamp, NULLABLE): Timestamp indicating when the user was last updated.

10. user_accesses
    Description: Maps users to accesses within the system.

    Table Structure:
    user_access_id (bigint UNSIGNED, PRIMARY KEY, AUTO_INCREMENT): Unique identifier for each user-access mapping.
    users_id (bigint UNSIGNED): Foreign key referencing users(users_id).
    access_id (bigint UNSIGNED): Foreign key referencing accesses(access_id).
    created_at (timestamp, NULLABLE): Timestamp indicating when the user-access mapping was created.
    updated_at (timestamp, NULLABLE): Timestamp indicating when the user-access mapping was last updated.

    Relationships:
    users_id references users(users_id) on DELETE CASCADE and UPDATE CASCADE.
    access_id references accesses(access_id) on DELETE CASCADE and UPDATE CASCADE.

## GAMBARAN RELASI 
   [Users] --< [User Access] >-- [Access] --< [Access Roles] >-- [Roles] --< [Role Permissions] >-- [Permissions]
      |
      |
[Personal Identity]
(User memiliki 1 Personal identity dan hanya 1 personal identity)


