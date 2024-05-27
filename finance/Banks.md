# 🏦 Banks

## Bank Accounts Entity
The following properties for fin_bank_accounts table:

| Name                      | Type      | Description                               | Unique | Required  |
|---------------------------|-----------|-------------------------------------------|--------|-----------|
| bank_account_id           | INT       | Primary key, unique bank account ID       |   ✅   |    ✅    |
| bank_account_number       | String(16)| Account number of the bank account        |   ❌   |    ✅    |
| bank_account_name         | String    | Receiver name of the bank account         |   ❌   |    ✅    |
| bank_type_id              | INT       | Foreign key from Bank Type table          |   ❌   |    ✅    |
| user_id                   | INT       | Foreign key from User table               |   ❌   |    ✅    |
| bank_id                   | INT       | Foreign key from Bank table               |   ❌   |    ✅    |


## Banks Entity
The following properties for fin_banks table:

| Name                      | Type      | Description                               | Unique | Required  |
|---------------------------|-----------|-------------------------------------------|--------|-----------|
| bank_id                   | INT       | Primary key, unique bank ID               |   ✅   |    ✅    |
| bank_name                 | String    | Name of the bank                          |   ❌   |    ✅    |
| bank_code                 | String    | Code of the bank                          |   ❌   |    ❌    |
| bank_logo                 | String    | Logo of the bank                          |   ❌   |    ❌    |
| bank_is_active            | boolean   | Is bank active (Default: True)            |   ❌   |    ✅    |


## Bank Type Entity
The following properties for fin_bank_types table:

| Name                      | Type      | Description                               | Unique | Required  |
|---------------------------|-----------|-------------------------------------------|--------|-----------|
| bank_type_id              | INT       | Primary key, unique bank ID               |   ✅   |    ✅    |
| bank_type_name            | String    | Name of the bank                          |   ❌   |    ✅    |
| bank_type_is_public       | boolean   | Is bank type public (Default: False)      |   ❌   |    ✅    |

Default Entity:
`[{'Admin',true},{'Nasabah',false}]`


## User Wallet Entity
The following properties for fin_user_wallets table:

| Name                      | Type      | Description                                | Unique | Required  |
|---------------------------|-----------|--------------------------------------------|--------|-----------|
| wallet_id                 | INT       | Primary key, unique wallet ID              |   ✅   |    ✅    |
| wallet_name               | String    | Name of the wallet                         |   ❌   |    ✅    |
| wallet_balance            | Decimal   | Total Balance of the wallet                |   ❌   |    ✅    |
| wallet_description        | String    | Description of the wallet                  |   ❌   |    ❌    |
| wallet_icon               | String    | Icon of the wallet                         |   ❌   |    ❌    |
| user_id                   | INT       | Foreign key from User table                |   ❌   |    ✅    |


## User Wallet Type Entity
The following properties for user_wallet_type table:

| Name                      | Type      | Description                               | Unique | Required  |
|---------------------------|-----------|-------------------------------------------|--------|-----------|
| wallet_type_id            | INT       | Primary key, unique bank ID               |   ✅   |    ✅    |
| wallet_type_name          | String    | Name of the bank                          |   ❌   |    ✅    |
| wallet_type_is_public     | boolean   | Is wallet type public (Default: False)    |   ❌   |    ✅    |
| wallet_type_is_active     | boolean   | Is wallet type public (Default: True)     |   ❌   |    ✅    |


NOTE
- Unique: Ensures the uniqueness of the values entered into a property of a database table.
- Required: Ensures that the values entered a property of a database table can NOT be NULL.

---
Powered by Berani Digital ID © 2024
