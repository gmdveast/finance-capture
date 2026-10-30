# Finance Capture

Capture financial transactions and view account balances in Obsidian Mobile. Transactions are stored inside your vault. Syncthing transfers them to the Finance desktop application, which imports them into an Excel workbook.

## Features

- Record income, expenses and transfers using accounts and reference lists synced from Finance.
- Keep queued JSON transactions and linked, read-only Markdown cards.
- View synced balances and a forecast including pending transactions.
- Embed independent capture, balance and queue management panels in notes.

## Installation and setup

1. Install and enable **BRAT** from Obsidian's community plugins.
2. In BRAT settings, choose **Add beta plugin**, enter `gmdveast/finance-capture`, and select the latest release.
3. Enable **Finance Capture**.
4. In the plugin settings, choose your author name, sync root inside the vault and operation card subfolder.
5. Configure Syncthing to sync this folder with Finance on your computer. Keep Finance running to import transactions and publish accounts and reference lists.

At least one synced active account is required to capture a transaction. Finance desktop is the only Excel writer. The plugin version is independent of the desktop version.

## Panels and commands

Use the command palette's **Добавить финансовую операцию** command to capture a transaction. Insert fenced code blocks named `finance-capture`, `finance-balances`, or `finance-capture-manager` for capture, balances, or queue management. Each note can host its own panel.

Editing a generated card does not change its queued JSON. Deleting a linked pending card while the plugin is active can cancel that queued transaction. An archived card indicates queue absence; only a matching receipt confirms import. Queue cleanup requires confirmation and applies only to plugin-generated files.

## Privacy and compatibility

The plugin uses Obsidian vault APIs and supports mobile and desktop. It makes no network requests, collects no telemetry, and does not access files outside the vault. Syncthing is a separate application: its configured peers receive the synced financial data. The plugin does not install or update itself; BRAT or Obsidian manages installation and updates.

Source files are the release assets: `main.js`, `manifest.json`, and `styles.css`; no build step is required. License: [MIT](LICENSE).

---

# Finance Capture для Obsidian

Мобильный плагин для ввода финансовых операций и просмотра балансов. Операции сохраняются в хранилище Obsidian; Syncthing передаёт их в desktop-приложение Finance, которое импортирует их в книгу Excel.

## Возможности

- Создание доходов, расходов и переводов по счетам и справочникам, синхронизированным из Finance.
- Очередь операций и связанные Markdown-карточки со статусом обработки.
- Панель балансов с текущими остатками и прогнозом с учётом ожидающих операций.
- Вставка формы, панели балансов и панели управления очередью в заметки.

Плагин работает в Obsidian Mobile и не отправляет финансовые данные напрямую в интернет. Для передачи между телефоном и компьютером настройте Syncthing.

## Установка и подключение

1. Установите и включите **BRAT** из каталога плагинов Obsidian.
2. В настройках BRAT выберите **Add beta plugin**, добавьте `gmdveast/finance-capture` и выберите последнюю версию.
3. Установите и включите **Finance Capture**.
4. В настройках Finance Capture задайте автора, корневую папку синхронизации и подпапку карточек.
5. Настройте Syncthing так, чтобы эта папка синхронизировалась с папкой Finance на компьютере. Запущенное desktop-приложение импортирует очередь и передаёт на телефон счета и справочники.

Для создания операции нужен хотя бы один синхронизированный активный счёт.

## Панели и команды

Откройте палитру команд Obsidian и выберите **Добавить финансовую операцию** для быстрого ввода. Команды **Вставить панель добавления операции в заметку**, **Вставить панель общих балансов в заметку** и **Вставить панель управления мобильными операциями в заметку** добавляют соответствующие панели в текущую заметку.

Лицензия: [MIT](LICENSE).

## Конфиденциальность и совместимость

Плагин использует API хранилища Obsidian, работает на телефоне и компьютере, не выполняет сетевых запросов, не собирает телеметрию и не обращается к файлам вне хранилища. Syncthing — отдельное приложение: настроенные устройства получают синхронизируемые финансовые данные. Установкой и обновлением управляет BRAT или Obsidian. Версия плагина не зависит от версии desktop.

Для панелей используются блоки кода `finance-capture`, `finance-balances` и `finance-capture-manager`. Редактирование карточки не меняет JSON. Удаление связанной ожидающей карточки при работающем плагине может отменить операцию в очереди. Архивная карточка означает отсутствие JSON в очереди; импорт подтверждается только соответствующей квитанцией. Очистка требует подтверждения и затрагивает только созданные плагином файлы.

Файлы релиза — `main.js`, `manifest.json` и `styles.css`; отдельная сборка не требуется.
