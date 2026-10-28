---
title: m.ledger Privacy Policy
permalink: /privacy/
---

# m.ledger Privacy Policy

**Effective date: October 28, 2026**

This policy describes how m.ledger handles information when you use the Android app. m.ledger is a personal accounting app built on double-entry bookkeeping. Google Drive and GitHub release checks are optional services with separate purposes.

## Information m.ledger handles

The app stores your books, accounts, entries, splits, import sources, and preferences in its local app data and database on your device (`mledger.db`). It processes data locally on your device to support account suggestions, local alerts, and dashboard calculations. An exported backup or CSV export contains your complete financial history, so store backup and export files somewhere you trust.

## Google Drive access

If you enable optional automatic backup to Google Drive, m.ledger uses the authorized connection (`drive.appdata` scope) to upload a backup ZIP file and access it for restoration. A backup contains your entire m.ledger database and preferences. Files are stored in a private app folder in your Google Drive and do not appear in your normal file list. 

You can disconnect your Google account or revoke m.ledger's access in your Google Account settings at any time. Disconnecting does not by itself remove information already stored in your local library or erase backups previously uploaded to Drive; delete those separately if you wish.

## Update checks

Once a day when you open the app, m.ledger checks GitHub to see if a new version exists. This is a public query that does not send any of your financial data.

## Storage, sharing, and your choices

Your accounting data is stored on your device. m.ledger sends data to Google Drive only for the optional Drive backup features you enable and queries GitHub for app updates. Files you export, back up, or share are handled by the destination you choose. m.ledger does not connect to your bank and never requests bank credentials.

You can record, edit, reverse, and reconcile entries, import CSV or OFX statements, browse dashboards and statements, and use local alerts without connecting a Google account. Google Drive backup requires an internet connection and a Google account connection.

You can delete data, clear app data, or uninstall the app through Android. Before clearing data or uninstalling, export a backup if you want to keep your library. You can manage Google Drive backups in your Drive account and revoke app access in your Google Account settings. Removing local data does not automatically delete copies that you previously exported or uploaded.

## Security and updates

Keep your Google account credentials and backup files private. This policy may change when m.ledger's features or data handling change. The effective date above identifies the current version; the updated policy will be published on this page.

## Contact

For privacy questions or requests, [open an issue in the m.ledger releases repository](https://github.com/GimmeCheez/mledger-releases/issues). Do not post financial data, names, account numbers, or other sensitive information in a public issue.

[Home]({{ '/' | relative_url }}) · [Terms of Use]({{ '/terms/' | relative_url }})