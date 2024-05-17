# 🧾 Journals

## Journals Entity
The following properties for acc_journals table:

| Name                      | Type      | Description                               | Unique | Required  |
|---------------------------|-----------|-------------------------------------------|--------|-----------|
| journal_id                | INT       | Primary key, unique journal entry ID      |   ✅   |    ✅    |
| journal_date              | DateTime  | Transaction date of the jorunal entry     |   ❌   |    ✅    |
| journal_description       | String    | Description of the Journal entry          |   ❌   |    ❌    |
| journal_reference         | String    | Reference of the journal entry            |   ❌   |    ❌    |
| user_id                   | String    | The identifier of the journal entry       |   ❌   |    ✅    |

## Journal Transactions Entity
The following properties for acc_journal_transactions table:

| Name                          | Type      | Description                                   | Unique | Required  |
|-------------------------------|-----------|-----------------------------------------------|--------|-----------|
| journal_id                    | INT       | Foreign key from Journals Table               |   ❌   |    ✅    |
| account_id                    | INT       | Foreign key from Account (CoA) Table          |   ❌   |    ✅    |
| transaction_type              | String    | Type of the transaction entry (Debit/Credit)  |   ❌   |    ✅    |
| transaction_total             | INT       | Total of the transaction entry                |   ❌   |    ✅    |
| transaction_description       | String    | Description of the transaction entry          |   ❌   |    ❌    |
| user_id                       | String    | The identifier of the transaction entry       |   ❌   |    ✅    |

NOTE
- Unique: Ensures the uniqueness of the values entered into a property of a database table.
- Required: Ensures that the values entered a property of a database table can NOT be NULL.

---
Powered by Berani Digital ID © 2024