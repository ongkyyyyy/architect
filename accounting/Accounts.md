# ✍️ Accounts

## Accountings Entity
The following properties for acc_accountings table:

| Name                      | Type      | Description                               | Unique | Required  |
|---------------------------|-----------|-------------------------------------------|--------|-----------|
| accounting_id             | INT       | Primary key, unique accounting ID         |   ✅   |    ✅    |
| accounting_name           | String    | Name of the accounting                    |   ❌   |    ✅    |
| accounting_description    | String    | Description of the accounting             |   ❌   |    ❌    |


## Categories Entity
The following properties for acc_categories table:

| Name                      | Type      | Description                               | Unique | Required  |
|---------------------------|-----------|-------------------------------------------|--------|-----------|
| category_id               | INT       | Primary key, unique category ID           |   ✅   |    ✅    |
| category_name             | String    | Name of the category                      |   ❌   |    ✅    |
| category_type             | String    | Type of the category (Debit/Credit)       |   ❌   |    ✅    |
| category_code             | String    | Code of the category                      |   ❌   |    ❌    |
| category_description      | String    | Description of the category               |   ❌   |    ❌    |
| accounting_id             | INT       | Foreign Key from Accountings table        |   ❌   |    ✅    |


## Accounts Entity
The following properties for acc_accounts table:

| Name                      | Type      | Description                                           | Unique | Required  |
|---------------------------|-----------|-------------------------------------------------------|--------|-----------|
| account_id                | INT       | Primary key, unique account ID                        |   ✅   |    ✅    |
| account_name              | String    | Name of the account                                   |   ❌   |    ✅    |
| account_type              | String    | Type of the account (Debit/Credit)                    |   ❌   |    ✅    |
| account_code              | String    | Code of the account                                   |   ❌   |    ❌    |
| account_description       | String    | Description of the account                            |   ❌   |    ❌    |
| account_parent_id         | INT       | Foreign Key from Acoount                              |   ❌   |    ❌    |
| category_id               | INT       | Foreign key from Categories Table                     |   ❌   |    ✅    |


NOTE
- Unique: Ensures the uniqueness of the values entered into a property of a database table.
- Required: Ensures that the values entered a property of a database table can NOT be NULL.

---
Powered by Berani Digital ID © 2024
