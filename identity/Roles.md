# 🔐 Roles
The roles and permissions are an important entities of the identity service. We will describe the role-related concepts and details in the following.

## Roles Entity
The following properties for identity_roles table:

| Name                  | Type      | Description                                      | Unique | Required  |
|-----------------------|-----------|--------------------------------------------------|--------|-----------|
| role_id               | String    | Primary key, unique role ID                      |   ✅   |    ✅    |
| role_name             | String    | Name of the role                                 |   ❌   |    ✅    |

## Permissions Entity
The following properties for identity_permissions table:

| Name                  | Type      | Description                                      | Unique | Required  |
|-----------------------|-----------|--------------------------------------------------|--------|-----------|
| permission_id         | String    | Primary key, unique permission ID                |   ✅   |    ✅    |
| permission_name       | String    | Description of the permission                    |   ❌   |    ✅    |

## Role Permissions Entity
The following properties for identity_role_permissions table (associative table for Roles and Permissions):

| Name                  | Type      | Description                                      | Unique | Required  |
|-----------------------|-----------|--------------------------------------------------|--------|-----------|
| role_id               | String    | Foreign key from Roles table                     |   ❌   |    ✅    |
| role_permission_id    | String    | Foreign key from Permissions table               |   ❌   |    ✅    |

## User Roles Entity
The following properties for identity_user_roles table (associative table for Users and Roles):

| Name             | Type      | Description                                      | Unique | Required  |
|------------------|-----------|--------------------------------------------------|--------|-----------|
| user_id          | String    | Foreign key from Users table                     |   ❌   |    ✅    |
| user_role_id     | String    | Foreign key from Roles table                     |   ❌   |    ✅    |

NOTE
- Unique: Ensures the uniqueness of the values entered into a property of a database table.
- Required: Ensures that the values entered a property of a database table can NOT be NULL.

---
Powered by Berani Digital ID © 2024
