# 💵 Transactions

## Transaction Entity
The following properties for fin_trx table:

| Name              | Type      | Description                                   | Unique | Required  |
|-------------------|-----------|-----------------------------------------------|--------|-----------|
| trx_id            | INT       | Primary key, unique transaction ID            |   ✅   |    ✅    |
| trx_amount        | Decimal   | Amount of the transaction                     |   ❌   |    ✅    |
| trx_proof         | String    | Proof of the transaction                      |   ❌   |    ❌    |
| trx_method_id     | INT       | Method of the transaction (Cash/Transfer)     |   ❌   |    ✅    |
| trx_type_id       | INT       | Type of the transaction (Deposit/Withdrawal)  |   ❌   |    ✅    |
| trx_status_id     | INT       | Status of the transaction                     |   ❌   |    ✅    |
| wallet_id         | INT       | Foreign key from Wallet table                 |   ❌   |    ❌    |
| bank_account_id   | INT       | Foreign key from Bank Account table           |   ❌   |    ❌    |
| user_id           | INT       | Foreign key from User table                   |   ❌   |    ✅    |


## Transaction Type Entity
The following properties for fin_trx_types table:

| Name                    | Type      | Description                                 | Unique | Required  |
|-------------------------|-----------|---------------------------------------------|--------|-----------|
| trx_type_id             | INT       | Primary key, unique bank ID                 |   ✅   |    ✅    |
| trx_type_code           | String(6) | Code of the transaction type                |   ❌   |    ✅    |
| trx_type_name           | String    | Name of the transaction type                |   ❌   |    ✅    |
| trx_type_is_public      | boolean   | Is transaction type public (Default: False) |   ❌   |    ✅    |

Default Entity:
`[{'1','Setoran'},{'2','Penarikan'},{'3','Transfer Keluar'},{'4','Transfer Masuk'}]`


## Transaction Method Entity
The following properties for fin_trx_methods table:

| Name                    | Type      | Description                                   | Unique | Required  |
|-------------------------|-----------|-----------------------------------------------|--------|-----------|
| trx_method_id           | INT       | Primary key, unique bank ID                   |   ✅   |    ✅    |
| trx_method_code         | String(6) | Code of the transaction method                |   ❌   |    ✅    |
| trx_method_name         | String    | Name of the transaction method                |   ❌   |    ✅    |
| trx_method_is_public    | boolean   | Is transaction method public (Default: False) |   ❌   |    ✅    |

Default Entity:
`[{'1','Cash/Tunai'},{'2','Bank Transfer'}]`


## Transaction Status Entity
The following properties for fin_trx_types table:

| Name                    | Type      | Description                                   | Unique | Required  |
|-------------------------|-----------|-----------------------------------------------|--------|-----------|
| trx_status_id           | INT       | Primary key, unique status ID                 |   ✅   |    ✅    |
| trx_status_code         | String(6) | Code of the transaction status                |   ❌   |    ✅    |
| trx_status_name         | String    | Name of the transaction status                |   ❌   |    ✅    |
| trx_status_is_public    | boolean   | Is transaction status public (Default: False) |   ❌   |    ✅    |

Default Entity:
`[{'0','Draft'},{'1','Approved'},{'2','Cancelled'},{'3','Pending'},{'9','Denied'}]`


NOTE
- Unique: Ensures the uniqueness of the values entered into a property of a database table.
- Required: Ensures that the values entered a property of a database table can NOT be NULL.

---
Powered by Berani Digital ID © 2024
