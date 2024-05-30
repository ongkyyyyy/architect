# 💰 Wallets

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
| wallet_account_type       | String    | Type of the wallet (Debit/Credit)         |   ❌   |    ✅    |
| wallet_type_is_public     | boolean   | Is wallet type public (Default: False)    |   ❌   |    ✅    |
| wallet_type_is_active     | boolean   | Is wallet type active (Default: True)     |   ❌   |    ✅    |
| wallet_type_is_credit     | boolean   | Is wallet type credit (Default: True)     |   ❌   |    ✅    |
| currency_id               | boolean   | Foreign key from Currency table           |   ❌   |    ✅    |

NOTE
- Unique: Ensures the uniqueness of the values entered into a property of a database table.
- Required: Ensures that the values entered a property of a database table can NOT be NULL.

## Wallet Account Type

A Wallet Account Type is a classification used to indicate the nature of transactions associated with a wallet. It helps differentiate between different types of wallets based on their primary purpose. There are two main account types:

1. Debit Wallet: A debit wallet is primarily used for saving and accumulating funds.
   - When a transaction occurs in a debit wallet, it is considered an addition (i.e., funds are added to the wallet).
   - Examples of debit wallets include personal savings accounts, emergency funds, and investment accounts.

2. Credit Wallet: A credit wallet is typically associated with loans, credit lines, or borrowed funds.
   - When a transaction occurs in a credit wallet, it is considered a reduction (i.e., funds are deducted from the wallet).
   - Examples of credit wallets include credit cards, student loans, and mortgages.

By clearly defining the wallet account type, users can better understand the purpose and expected behavior of their wallets. Whether it's for saving or borrowing, choosing the right account type ensures effective financial management. 😊


---
Powered by Berani Digital ID © 2024
