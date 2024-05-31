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

1. Account Debit Wallet: A debit wallet is primarily used for saving and accumulating funds.
   - When a transaction occurs in a debit wallet, it is considered an addition (i.e., funds are added to the wallet).
   - Examples of debit wallets include personal savings accounts, emergency funds, and investment accounts.

2. Account Credit Wallet: A credit wallet is typically associated with loans, credit lines, or borrowed funds.
   - When a transaction occurs in a credit wallet, it is considered a reduction (i.e., funds are deducted from the wallet).
   - Examples of credit wallets include credit cards, student loans, and mortgages.
   
3. Public Wallet: A public wallet is accessible by all users, allowing them to view its balance and transaction history.
   - By default, wallets are not public. In other words, users cannot directly access or transact with a public wallet. Only administrators or designated personnel have the authority to manage and withdraw funds from a public wallet. It serves as a transparent account for various purposes.
   - Examples of public wallets include collaborative, sharing, and kindness wallet for a common cause.

4. Active Wallet: An active wallet represents the current operational state of the wallet.
   - The status of the wallet determines whether users can perform transactions with it.
   - Examples of inactive wallets include unauthorized access attempts, security concerns, or other exceptional cases.

5. Is Credit Wallet: A wallet represents the transactional wallet accessible to the user by default.
   - In contrast, a non credit wallet is not directly transactable by the user. Instead, it is managed by an administrator or system. Users cannot directly initiate transactions with a non credit wallet. When a user wants to transact with a private wallet, they can initiate the process by making a request.
   - Examples of non credit wallets include reserved funds that are not available for regular transactions.

By clearly defining the wallet account type, users can better understand the purpose and expected behavior of their wallets. Whether it's for saving or borrowing, choosing the right account type ensures effective financial management. 😊


---
Powered by Berani Digital ID © 2024
