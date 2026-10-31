# Finance Capture

Capture financial transactions and view account balances in Obsidian Mobile. Transactions are stored inside your vault. Syncthing transfers them to the Finance desktop application, which imports them into an Excel workbook.

## Features

- Record income, expenses and transfers using accounts and reference lists synced from Finance.
- Keep queued JSON transactions and linked, read-only Markdown cards.
- View synced balances and a forecast including pending transactions.
- Embed independent capture, balance and queue management panels in notes.

## Installation and setup

After the plugin is approved and listed in the Community Plugins directory:

1. In Obsidian, open **Settings → Community plugins → Browse**, search for **Finance Capture**, select **Install**, and then enable it.
2. In the plugin settings, choose your author name, sync root inside the vault, and operation card subfolder.
3. Configure Syncthing to sync this folder with Finance on your computer. Keep Finance running to import transactions and publish accounts and reference lists.

For beta testing before the directory listing is available, install **BRAT**, choose **Add beta plugin**, and enter `gmdveast/finance-capture`.

At least one synced active account is required to capture a transaction. Finance desktop is the only Excel writer. The plugin version is independent of the desktop version.

## Panels and commands

Use Obsidian's command palette to capture a transaction. Insert fenced code blocks named `finance-capture`, `finance-balances`, or `finance-capture-manager` for capture, balances, or queue management. Each note can host its own independent panel.

Editing a generated card does not change its queued JSON. Deleting a linked pending card while the plugin is active can cancel that queued transaction. An archived card indicates queue absence; only a matching receipt confirms import. Queue cleanup requires confirmation and applies only to plugin-generated files.

## Privacy and compatibility

The plugin uses Obsidian vault APIs and supports mobile and desktop. It makes no network requests, collects no telemetry, and does not access files outside the vault. Syncthing is a separate application: its configured peers receive the synced financial data. The plugin does not install or update itself; BRAT or Obsidian manages installation and updates.

Source files are the release assets: `main.js`, `manifest.json`, and `styles.css`; no build step is required. License: [MIT](LICENSE).
