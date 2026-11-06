# Finance Capture

Finance Capture is the Obsidian companion to **Finance**, a local Windows app for personal finance. Use Obsidian on your phone to record income, expenses, and transfers, check synced balances, and manage transactions waiting to reach your computer.

Finance desktop owns the Excel workbook and is the only app that writes to it. Finance publishes account, category, and balance data to a sync folder. This plugin reads that data and saves new transactions in your vault; Syncthing transfers them to Finance desktop for import.

## Project links

- [Finance desktop app](https://github.com/gmdveast/finance-desktop)
- [Finance desktop releases](https://github.com/gmdveast/finance-desktop/releases)
- [Finance Capture source repository](https://github.com/gmdveast/finance-capture)
- [Finance Capture releases](https://github.com/gmdveast/finance-capture/releases)
- [Report a plugin issue](https://github.com/gmdveast/finance-capture/issues)
- [Finance Capture in the Obsidian Community directory](https://community.obsidian.md/plugins/finance-capture)

The desktop app and plugin are released separately. Install or update the desktop app from its releases page; install or update the plugin through Obsidian.

## Features

- Record income, expenses, and transfers using accounts and reference lists synced from Finance desktop.
- Save queued transactions as JSON files and create linked, read-only Markdown cards.
- View synced account balances and a forecast that includes eligible pending transactions.
- Add independent capture, balance, and queue-management panels to notes.
- Use English or Russian, or follow the language configured in Obsidian.

## Requirements

- Obsidian 1.14.0 or later on desktop or mobile.
- Finance desktop on Windows x64.
- Syncthing configured to sync Finance's phone folder with a folder inside your Obsidian vault.

At least one active account must be synced before you can capture a transaction. Keep Finance desktop running to publish updated accounts and reference lists and to import the queue.

Choose **Settings → Finance Capture → Language** to select English or Russian, or follow Obsidian's language. Account and category names remain as defined in Finance desktop.

## Install and set up

1. In Obsidian, open **Settings → Community plugins → Browse**, search for **Finance Capture**, install it, and enable it. You can also open the [Community directory listing](https://community.obsidian.md/plugins/finance-capture).
2. Install and open [Finance desktop](https://github.com/gmdveast/finance-desktop/releases). In Finance, use **Connect phone** to find the folder to sync.
3. Configure Syncthing to sync that folder with a folder inside your vault. Keep the Finance and vault folders in sync; do not point the plugin at a folder outside the vault.
4. In the plugin settings, set the author name, the matching sync folder inside the vault, and the subfolder for operation cards.
5. Wait for the account list to sync, then capture a transaction from the command palette or a note panel.

## Capture panels and queue

Use the command palette to add a financial operation or insert one of these code blocks in a note:

| Code block | Purpose |
| --- | --- |
| `finance-capture` | Capture an operation in the note. |
| `finance-balances` | View synced balances and the pending-transaction forecast. |
| `finance-capture-manager` | Review and clean up plugin-managed cards and queued JSON. |

Each note can host its own independent panel. The plugin also provides a command to show how many operations and receipts are in the sync folder.

Generated Markdown cards are read-only summaries; editing a card does not change its queued JSON. Deleting a linked card can cancel its transaction only while that transaction is still pending and the plugin can validate the link. An archived card means its JSON is no longer in the queue; a matching receipt is needed to confirm that Finance imported it. Queue cleanup requires confirmation and only targets plugin-managed files.

## Privacy and compatibility

The plugin uses Obsidian's vault APIs and makes no network requests. It does not access files outside the vault or collect telemetry. Transaction JSON and cards are stored in the vault, so Syncthing sends them to the peers you configure. Finance desktop separately fetches exchange rates from the Central Bank of Russia and checks GitHub for desktop updates.

The plugin works on Obsidian mobile and desktop. It does not write to the Finance workbook, install itself, or update Finance desktop. Obsidian manages plugin updates independently from the desktop app.

Manual captures continue to use operation schema 1. The plugin also recognizes valid automatic-operation schema 2 files in the shared queue for pending-balance forecasts, card archiving, cancellation of a still-pending linked event, and reset cleanup. Unknown fields and malformed schema 2 events are excluded from forecasts and retained during cleanup.

The release consists of `main.js`, `manifest.json`, and `styles.css`; no build step is required. See the [source repository](https://github.com/gmdveast/finance-capture) for development. Report problems through [GitHub Issues](https://github.com/gmdveast/finance-capture/issues). License: [MIT](LICENSE).
