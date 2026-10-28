# m.ledger

**Record with rigor. Check it against your statement. See your net worth clearly.**

m.ledger is a personal accounting app for Android, built on double-entry bookkeeping. Organize your money into books, accounts, and entries, import bank statements, check each movement, and follow your net worth, income, and expenses on a dashboard, all stored on your device.

Every entry balances to zero, nothing is erased silently, and corrections leave a trail. Instead of a loose list of expenses, you get accounting you can query, audit, and export.

**For Android 14.0 or later.** Interface in Brazilian Portuguese and English.

## What you can do

### Organize your finances into books and accounts

Each **book** is an independent set of accounts with its own currency (BRL, USD, EUR, or another code of 2 to 12 characters). Use one book for your personal finances and another for a project or a second currency.

Inside a book, **accounts** come in five types:

| Type | What it represents | Examples |
| :--- | :--- | :--- |
| Assets | Money and property you own. | Checking Account, Savings, Investments |
| Liabilities | Debts. | Credit Card, Loans |
| Income | Money coming in. | Salary, Dividends |
| Expenses | Money spent. | Food, Housing, Transportation |
| Equity | Counterpart of opening balances and contributions. | Opening Balance |

When you create a book, you can turn on **Create suggested accounts** to start with 73 accounts already organized in a hierarchy (for example, Food → Groceries, Restaurants, Delivery), named in Portuguese or English depending on the language you chose. Accounts can be renamed, moved under another parent account of the same type, archived and, if empty, deleted.

### Record entries

Every entry has an **origin**, where the amount comes from (recorded as negative), and a **destination**, where the amount goes (recorded as positive). The postings always add up to zero.

Type only the digits of the amount: the sign is applied automatically and the last digits are the cents. For example, `13` becomes `0,13` and `130000` becomes `1.300,00` in BRL (`1,300.00` in USD).

| Situation | Origin (−) | Destination (+) |
| :--- | :--- | :--- |
| Debit card purchase | Checking account | Food |
| Credit card purchase | Credit card | Restaurants |
| Salary received | Salary | Checking account |
| Credit card bill payment | Checking account | Credit card |
| Transfer | Source account | Destination account |

For split entries, add more postings: the entry can only be saved when the sum is zero. The **Swap origin and destination** button flips the two sides with one tap.

Over time, the app learns from your history and can suggest accounts based on the description and amount. The suggestion is calculated on the device itself, never overwrites a choice you made, and should be reviewed before saving.

**Opening balance.** After creating an asset or liability account, open the account's actions and use **Opening balance** to enter how much it held on the date before your first entry: positive for money you have, negative for debt you owe. For a credit card, use the amount actually owed, not the limit. The equity counterpart is created automatically.

### Correct without erasing

Entries are never deleted. To undo an entry, use **Reverse**: the app creates an opposite entry and marks the original as **Reversed**. To correct one, use **Edit**: the original is reversed and a new version, linked to it, is created. Everything stays in the audit trail and can be seen by turning on **Show reversed entries** in the filters.

The app also blocks an entry that is identical to an existing one (same date, description, accounts, and amounts), preventing accidental duplicates.

### Check against your statement

**Reconcile** compares an entry with an independent statement: you enter the account, date, and amount as they appear on the statement. If anything differs, reconciliation is blocked until you correct the entry. Reconciled entries change from **Pending** to **Reconciled**, and you can undo a reconciliation whenever you like.

This check validates one entry at a time. It does not verify the statement's closing balance or find missing entries.

### Import CSV and OFX statements

Bring in your bank's transactions without typing anything.

| Format | What the app recognizes |
| :--- | :--- |
| CSV | Date and amount columns (description is optional), separated by commas or semicolons. Dates as `YYYY-MM-DD`, `DD/MM/YYYY`, or `MM/DD/YYYY`. |
| OFX | Statement transactions, with the bank's `FITID` identifier kept to prevent re-importing. |

Step by step:

1. In **New entry**, choose **Import CSV/OFX**.
2. Select the **bank account** and the default **offset account**.
3. Choose the file on your device.
4. Review the rows: possible duplicates are flagged and unchecked by default, and each row can have its own offset account.
5. Confirm the import.

If the amounts show up with the wrong sign, use **Invert statement signs**. Credit card CSVs in the Nubank format (columns `date`, `title`, and `amount`) have their signs adjusted automatically when the chosen account is a liability. Imported entries are created already **reconciled** against the original statement data.

Use files exported by the bank, encoded as UTF-8. Files in other encodings may show incorrect accented characters.

### Follow along on the Dashboard

The **Dashboard** brings together the main figures for the active book:

- **Net worth, Assets, and Liabilities:** current total balances, unrelated to the selected period.
- **Income and Expenses:** totals for the selected period.

Choose the period from **Last day**, **Last week**, **Last month**, and **All time**, or pick the dates on the calendar. Three charts help you interpret the numbers:

- **Monthly cash flow:** bars for income and expenses by month. Tap a month or use the arrows to see the values, and swipe to explore the period. Bars below zero represent reversals or refunds.
- **Categories for this period:** a donut chart with expenses (or income) grouped by top-level account. Tap a slice or a row in the list to see the amount. Slices compare net amounts in absolute value.
- **Net worth over time:** a line with cumulative net worth at the end of each month, up to the period's end date. Months with no activity carry over the previous month's balance.

The eye icon at the top hides amounts across the whole app, including the charts.

### Browse the Ledger and account statements

On the **Ledger** tab, search by description and filter by account, status (all, pending, or reconciled), and reversed entries. Each card shows the date, status, description, and the postings with their amounts.

On the **Accounts** tab, see the hierarchy with the accumulated balances of each account and its subaccounts. Tap an account to open its **Statement**, with every movement and the running balance line by line.

### Get local alerts

The bell at the top gathers alerts calculated on your device from your **reconciled** entries:

- **Learned recurrences:** when an expense or income appears four times in a row with the same description, the same accounts, and the same amount, at a monthly, biweekly, or weekly interval, the app creates a **pending** entry on the expected date. Check your statement before reconciling it. You can edit it, reverse it, or **Pause this pattern**.
- **Spending level changes:** when an expense account shifts to a new level persistently over complete weeks, the app notifies you with the weekly average before and after. It is a descriptive alert, not a forecast.

Automatic entries are estimates and are never reconciled on their own.

### Export, back up, and restore

In **Settings**, you will find three distinct features:

- **Export CSV:** generates a ZIP with `books.csv`, `accounts.csv`, `transactions.csv`, and `splits.csv`, linked by ID, for the chosen period or the entire history. There is a profile for Brazilian Excel (semicolon and BOM). Amounts are kept in minor units to preserve accuracy. It is a reference file, not a restore file.
- **Backup:** saves all books, accounts, entries, import sources, and preferences in a ZIP verifiable by SHA-256.
- **Restore:** replaces the data on the device with an m.ledger backup.

## Getting started

### 1. Install and open the app

Install the Android installation file (APK) provided by the project. If Android asks for permission to install this way, follow the instructions shown on your device.

**Android .0 or later** is required. Everything works without a Google account and without internet. Once a day, when you open the app, it checks whether a new version exists and, if so, offers the download.

### 2. Meet the starter book

On first launch, m.ledger creates the **Pessoal** book, in BRL, already with the suggested accounts. To create another book, tap the book name at the top and choose **New book**. The book marked as default is only identified in the list: the app reopens on the last book you used.

### 3. Enter opening balances

On the **Accounts** tab, open each asset or liability account that already holds a balance and use **Opening balance**. This makes the Dashboard's net worth start out correct.

### 4. Record or import your first entries

Tap **New entry** to record a movement, or use **Import CSV/OFX** to bring in a statement. Starting with one month makes it easier to get to know the app before importing your whole history.

### 5. Reconcile and check the Dashboard

Reconcile the entries you typed by comparing them with the statement, and check income, expenses, and net worth on the Dashboard. Reconciled entries also feed the local alerts.

### 6. Set up a backup

In Settings, make a **Backup** and keep the file outside your device, or turn on automatic backup to Google Drive. We recommend keeping this protection active, since all your data is otherwise stored only locally.

## Automatic backup to Google Drive (optional)

To turn it on:

1. Open **Settings** and find the **Google Drive** section.
2. Turn on **Automatic backup**.
3. Choose the Google account and authorize the requested access.
4. Wait for the first upload and check the date of the last completed backup.

The app only asks for the `drive.appdata` permission, which gives access to a private folder belonging to m.ledger itself. The files do not appear in your normal Drive file list. After each change (with a wait of about 10 seconds) and every six hours, a new backup is uploaded whenever there is a connection. Android may delay execution to save battery, so check the status on the Settings screen. The five most recent versions from each device are kept.

Use **Back up now** to force an upload and **Restore from Drive** to list the saved versions and restore one of them. If the authorization expires, the app shows **Reconnect Google account**. Turning off automatic backup does not delete the files that are already in Drive.

This feature requires internet and Google Play Services on the device. It is a backup of the entire ledger: **it is not syncing or merging between devices**.

## Offline use and optional services

| Feature | Needs internet? |
| :--- | :--- |
| Record, edit, reverse, and reconcile entries | No. |
| Import a CSV or OFX statement available on the device | No. |
| Browse the Dashboard, the Ledger, and statements | No. |
| Get account suggestions and local alerts | No. |
| Export CSV and back up or restore through a file | No. |
| Check for a new version of the app | Yes, once a day. |
| Automatic backup and recovery through Google Drive | Yes. |

Alerts and automatic entries are checked when the app opens and, in the background, every 12 hours. Android may delay automatic tasks depending on battery and connection conditions.

## Your data and your choices

All your accounting is saved on the device. Google Drive is an optional connection that you turn on yourself.

- **Update check:** a public query to the versions published on GitHub, without sending your financial data.
- **Google Drive:** stores a complete backup copy in the app's private folder, when backup is enabled.
- **Backup and export:** the files are **not encrypted** and contain your entire history. Keep them somewhere you trust.
- **Access protection:** m.ledger has no password or biometrics of its own. It relies on the device's screen lock.
- **Delete all data:** in Settings, permanently removes local books, accounts, entries, and preferences. It requires two confirmations, one of them by typing a phrase. It does not delete backups that are already in Drive.

This is an early version. Test the app on your own device before trusting it with real financial data, and keep your backups up to date.

## Backup and restore

Use **Backup** in Settings to create the copy and **Restore** to recover it. The file is verified (integrity, references between accounts and entries, balances, and preferences) before anything is changed.

**Restoring replaces all current data in the app.** If you want to keep it, make a backup before continuing. Restoring or deleting data turns off automatic Drive backup: reconnect after checking that everything is correct.

Before switching devices, clearing data, or uninstalling m.ledger, make sure your copy is up to date.

## Frequently asked questions

### Do I need internet or a Google account?

No. Only the Google Drive backup requires a Google account and a connection. The daily update check is optional in practice: if it fails, the app carries on as normal.

### Does m.ledger connect to my bank?

No. You import CSV or OFX files exported by your bank, or record entries manually. No bank credentials are ever requested.

### Can I use more than one currency?

Yes, in separate books: each book has a single currency and there is no conversion between them. You switch between books by tapping the book name at the top.

### Is my data synced between devices?

No. The Drive backup stores versions per device, and restoring replaces all data on the current device. There is no merging of two devices.

### Can I delete an entry?

No: use **Reverse**, which preserves the history. Empty accounts and books (with no entries) can be deleted. Accounts with history can be **archived**, which blocks new entries and keeps the balance and history in reports.

### Why does the app say an identical entry already exists?

Because there is an active entry with the same date, description, accounts, and amounts. Check the Ledger. Entries with no description are not subject to this check.

### Why can't I reconcile an entry?

The account, date, or amount you entered differs from the entry, or from the original statement saved at import. Correct the entry, or review the data you entered, and try again.

### Can I import the same statement again?

Yes. In OFX, the bank's `FITID` prevents re-imports. In CSV, rows that were already imported are recognized and possible duplicates are flagged in the review. Even so, check the review before importing.

### My CSV was rejected. What should I check?

The file needs recognizable date and amount columns (for example, `data` and `valor`, or `date` and `amount`), dates in the accepted formats, and amounts with at most one decimal separator, such as `1234,56` or `1.234,56`. Values like `1.234`, with only a single dot, are read as decimals. Prefer UTF-8.

### Pending entries showed up that I didn't type. What are they?

They are learned recurrences. The app detected a fixed pattern in your reconciled entries and created the next one for the expected date. Edit it, reverse it, or pause the pattern from the bell, and reconcile it after checking your statement.

### I changed the language and the account names stayed the same. Why?

The names of the suggested accounts are saved when the book is created. Changing the language changes the interface, not the names already saved, which you can rename.

### Does the app work on iPhone or on versions older than Android 14.0?

No. This version is intended for devices running Android 14.0 or later.

## Report a problem or suggest an improvement

Use this repository's **Issues** tab. To make the analysis easier, include:

- What you tried to do and what happened.
- The steps to reproduce the problem.
- The m.ledger version (in Settings), the device model, and the Android version.
- A screenshot, if it helps explain.

Before attaching files or images, remove financial data, names, account numbers, and any personal information. Never post real backups or statements.
