# m.ledger

**Record with rigor. Check against your statement. See your net worth clearly.**

m.ledger is a personal accounting app for Android, built on double-entry bookkeeping. Organize your money into books, accounts, and entries, import bank statements, verify every transaction, and track your net worth, income, and expenses on a dashboard, all stored on your device.

Every entry sums to zero, nothing is silently deleted, and corrections leave a trail. Instead of a loose list of expenses, you get accounting you can query, audit, and export.

**For Android 8.0 or later.** Interface in Brazilian Portuguese and English.

## What you can do

### Organize your finances into books and accounts

Each **book** is an independent set of accounts with its own currency (BRL, USD, EUR, or any other code from 2 to 12 characters). Use one book for your personal finances and another for a project or a second currency.

Within a book, **accounts** fall into five types:

| Type | What it represents | Examples |
| :--- | :--- | :--- |
| Assets | Money and property you own. | Checking account, Savings, Investments |
| Liabilities | Debts. | Credit card, Loans |
| Income | Money coming in. | Salary, Dividends |
| Expenses | Spending. | Food, Housing, Transportation |
| Equity | Offset for opening balances and capital contributions. | Opening balance |

When you create a book, you can check **Create suggested accounts** to start with 73 accounts already organized into a hierarchy (for example, Food → Groceries, Restaurants, Delivery), named in Portuguese or English depending on the language you choose. Accounts can be renamed, moved under another parent account of the same type, archived, and, if empty, deleted.

### Record entries

Every entry has an **origin**, where the value comes from (recorded as negative), and a **destination**, where the value goes (recorded as positive). The splits always add up to zero.

Type only the digits of the amount: the sign is applied automatically and the last digit represents the cents. For example, `13` becomes `0,13` and `130000` becomes `1.300,00` in BRL (`1,300.00` in USD).

| Situation | Origin (−) | Destination (+) |
| :--- | :--- | :--- |
| Debit card purchase | Checking account | Food |
| Credit card purchase | Credit card | Restaurants |
| Salary received | Salary | Checking account |
| Credit card bill payment | Checking account | Credit card |
| Transfer | Source account | Destination account |

For split entries, add more splits: the entry can only be saved when the sum is zero. The **Swap origin and destination** button flips the two sides with a single tap.

Over time, the app learns from your history and can suggest accounts based on the description and amount. The suggestion is computed on your device, never overrides a choice you made, and should be reviewed before saving.

**Opening balance.** After you create an asset or liability account, open the account's actions and use **Opening balance** to enter how much was in it on the day before your first entry: positive for money you have, negative for debt. For a credit card, use the amount actually owed, not the credit limit. The equity offset is created automatically.

### Correct without deleting

Entries are never deleted. To undo an entry, use **Reverse**: the app creates an opposite entry and marks the original as **Reversed**. To correct one, use **Edit**: the original is reversed and a new version, linked to it, is created. Everything stays in the audit trail and can be viewed by turning on **Show reversed entries** in the filters.

The app also blocks an entry identical to one that already exists (same date, description, accounts, and amounts), preventing accidental duplicates.

### Check against your statement

**Reconcile** compares an entry against an independent statement: you enter the account, date, and amount as they appear on the statement. If any detail differs, reconciliation is blocked until you fix the entry. Reconciled entries change from **Pending** to **Reconciled**, and you can undo the reconciliation at any time.

This check validates one entry at a time. It does not verify the statement's closing balance or find missing transactions.

### Import CSV and OFX statements

Bring in your bank transactions without typing anything.

| Format | What the app recognizes |
| :--- | :--- |
| CSV | Date and amount columns (description is optional), separated by commas or semicolons. Dates in `YYYY-MM-DD`, `DD/MM/YYYY`, or `MM/DD/YYYY`. |
| OFX | Statement transactions, with the bank's `FITID` identifier stored to prevent re-importing. |

Step by step:

1. In **New entry**, choose **Import CSV/OFX**.
2. Select the **bank account** and the default **offset account**.
3. Choose the file on your device.
4. Review the rows: possible duplicates are flagged and unchecked by default, and each row can have its own offset account.
5. Confirm the import.

If the amounts appear with the wrong sign, use **Invert statement signs**. Credit card CSVs in the Nubank format (columns `date`, `title`, and `amount`) have their signs adjusted automatically when the chosen account is a liability. Imported entries are created already **reconciled** against the original statement data.

Use files exported by the bank, encoded as UTF-8. Files in other encodings may display accents incorrectly.

### Track it on the Dashboard

The **Dashboard** gathers the key numbers for the active book:

- **Net worth, Assets, and Liabilities:** current total balances, regardless of the selected period.
- **Income and Expenses:** totals for the selected period.

Choose the period from **Last day**, **Last week**, **Last month**, and **All time**, or pick dates on the calendar. Three charts help you interpret the numbers:

- **Monthly cash flow:** bars of income and expenses by month. Tap a month or use the arrows to see the values, and swipe to explore the period. Bars below zero represent reversals or refunds.
- **Categories for this period:** a donut chart with expenses (or income) grouped by top-level account. Tap a slice or a row in the list to see the amount. Slices compare the absolute net amounts.
- **Net worth over time:** a line showing cumulative net worth at the end of each month, up to the period's end date. Months without activity keep the previous month's balance.

The eye icon at the top hides the amounts throughout the app, including in the charts.

### Browse the Ledger and account statements

In the **Ledger** tab, search by description and filter by account, status (all, pending, or reconciled), and reversed entries. Each card shows the date, status, description, and the splits with their amounts.

In the **Accounts** tab, see the hierarchy with the cumulative balances of each account and its subaccounts. Tap an account to open its **Statement**, with every transaction and the running balance line by line.

### Get local alerts

The bell at the top gathers alerts computed on your device from your **reconciled** entries:

- **Learned recurrences:** when an expense or income appears four times in a row with the same description, the same accounts, and the same amount, at a monthly, biweekly, or weekly interval, the app creates a **pending** entry on the expected date. Check your statement before reconciling. You can edit it, reverse it, or **Pause this pattern**.
- **Changes in spending level:** when an expense account shifts to a new level persistently over complete weeks, the app alerts you with the weekly average before and after. It is a descriptive alert, not a forecast.

Automatic entries are estimates and are never reconciled on their own.

### Export, back up, and restore

In **Settings**, you will find three separate features:

- **Export CSV:** generates a ZIP with `books.csv`, `accounts.csv`, `transactions.csv`, and `splits.csv`, linked by identifier, for the period you choose or your entire history. There is a profile for Brazilian Excel (semicolon and BOM). Amounts are stored in minor units to preserve accuracy. It is a reference file, not a restore file.
- **Backup:** saves all books, accounts, entries, import sources, and preferences in a ZIP verifiable by SHA-256.
- **Restore:** replaces the data on the device with an m.ledger backup.

## Getting started

### 1. Install and open the app

Install the Android installation file (APK) provided by the project. If Android asks for permission to install from this source, follow the instructions shown on the device.

**Android 8.0 or later** is required. Everything works without a Google account and without internet. Once a day, when you open the app, it checks for a new version and, if there is one, offers the download.

### 2. Meet your starter book

On first launch, m.ledger creates the **Personal** book, in BRL, already with the suggested accounts. To create another book, tap the book name at the top and choose **New book**. The book marked as default is only identified in the list: the app reopens on the last book you used.

### 3. Enter your opening balances

In the **Accounts** tab, open each asset or liability account that already has a balance and use **Opening balance**. This makes the Dashboard's net worth start out correct.

### 4. Record or import your first entries

Tap **New entry** to record a transaction or use **Import CSV/OFX** to bring in a statement. Starting with a single month makes it easier to get to know the app before importing your entire history.

### 5. Reconcile and check the Dashboard

Reconcile the entries you typed by comparing them with your statement, and check income, expenses, and net worth on the Dashboard. Reconciled entries also feed the local alerts.

### 6. Set up a backup

In Settings, make a **Backup** and keep the file off your device, or turn on automatic backup to Google Drive. We recommend keeping this protection on, since all your data is stored only locally.

## Automatic Google Drive backup (optional)

To turn it on:

1. Open **Settings** and find the **Google Drive** section.
2. Turn on **Automatic backup**.
3. Choose your Google account and grant the requested access.
4. Wait for the first upload and check the date of the last completed backup.

The app requests only the `drive.appdata` permission, which gives access to a private folder belonging to m.ledger itself. The files do not appear in your normal Drive file list. After each change (with a wait of about 10 seconds) and every six hours, a new backup is uploaded when a connection is available. Android may delay the run to save battery, so check the status on the Settings screen. The five most recent versions from each device are kept.

Use **Back up now** to force an upload and **Restore from Drive** to list the saved versions and restore one. If the authorization expires, the app shows **Reconnect Google account**. Turning off automatic backup does not delete the files already in Drive.

This feature requires internet and Google Play Services on the device. It is a full-book backup: **it is not syncing or merging between devices**.

## Offline use and optional services

| Feature | Needs internet? |
| :--- | :--- |
| Recording, editing, reversing, and reconciling entries | No. |
| Importing a CSV or OFX statement available on the device | No. |
| Viewing the Dashboard, the Ledger, and statements | No. |
| Getting account suggestions and local alerts | No. |
| Exporting CSV and backing up or restoring from a file | No. |
| Checking for a new app version | Yes, once a day. |
| Automatic backup and recovery through Google Drive | Yes. |

Alerts and automatic entries are checked when the app opens and, in the background, every 12 hours. Android may delay automatic tasks depending on battery and connection conditions.

## Your data and your choices

All your accounting is stored on the device. Google Drive is an optional connection that you turn on yourself.

- **Update check:** a public query to the versions published on GitHub, without sending your financial data.
- **Google Drive:** stores a full backup in the app's private folder, when backup is enabled.
- **Backup and export:** the files are **not encrypted** and contain your entire history. Keep them in a trusted location.
- **Access protection:** m.ledger has no password or biometrics of its own. It relies on the device's screen lock.
- **Delete all data:** in Settings, permanently removes books, accounts, entries, and local preferences. It requires two confirmations, one of them by typing a phrase. It does not delete backups already in Drive.

This is an early version. Validate the app on your device before trusting it with real financial data, and keep your backups up to date.

## Backup and restore

Use **Backup** in Settings to create the copy and **Restore** to recover it. The file is verified (integrity, references between accounts and entries, balances, and preferences) before any change is made.

**Restoring replaces all of the app's current data.** If you want to keep it, make a backup before continuing. Restoring or deleting your data turns off automatic Drive backup: reconnect after checking that everything is correct.

Before switching devices, clearing data, or uninstalling m.ledger, confirm that your copy is up to date.

## Frequently asked questions

### Do I need internet or a Google account?

No. Only the Google Drive backup requires a Google account and a connection. The daily update check is effectively optional: if it fails, the app carries on normally.

### Does m.ledger connect to my bank?

No. You import CSV or OFX files exported by your bank, or record entries manually. No banking credentials are ever requested.

### Can I use more than one currency?

Yes, in separate books: each book has a single currency and there is no conversion between them. You switch between books by tapping the book name at the top.

### Is my data synced between devices?

No. The Drive backup stores versions per device, and restoring replaces all data on the current device. There is no merging of two devices.

### Can I delete an entry?

No: use **Reverse**, which preserves the history. Empty accounts and books (with no entries) can be deleted. Accounts with history can be **archived**, which blocks new entries and keeps the balance and history in reports.

### Why does the app say an identical entry already exists?

Because there is an active entry with the same date, description, accounts, and amounts. Check the Ledger. Entries without a description are not subject to this check.

### Why can't I reconcile an entry?

The account, date, or amount you entered differs from the entry, or from the original statement saved during import. Fix the entry or review the data you entered and try again.

### Can I import the same statement again?

Yes. In OFX, the bank's `FITID` prevents re-imports. In CSV, rows that were already imported are recognized and possible duplicates are flagged in the review. Even so, check the review before importing.

### My CSV was rejected. What should I check?

The file needs recognizable date and amount columns (for example, `data` and `valor`, or `date` and `amount`), dates in the accepted formats, and amounts with at most one decimal separator, such as `1234,56` or `1.234,56`. Values like `1.234`, with a single period, are read as decimals. Prefer UTF-8.

### Pending entries I didn't type have appeared. What are they?

They are learned recurrences. The app detected a fixed pattern in your reconciled entries and created the next one for the expected date. Edit, reverse, or pause the pattern from the bell, and reconcile after checking your statement.

### I changed the language and the account names stayed the same. Why?

The names of suggested accounts are saved when the book is created. Changing the language changes the interface, not the names already saved, which you can rename.

### Does the app work on iPhone or on versions earlier than Android 8.0?

No. This version is intended for devices running Android 8.0 or later.

## Report a problem or suggest an improvement

Use this repository's **Issues** tab. To make the analysis easier, include:

- What you tried to do and what happened.
- The steps to reproduce the problem.
- The m.ledger version (in Settings), the device model, and the Android version.
- A screenshot, if it helps explain the issue.

Before attaching files or images, remove financial data, names, account numbers, and any personal information. Never post real backups or statements.
