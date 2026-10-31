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

Use the command palette's **Добавить финансовую операцию** command to capture a transaction. Insert fenced code blocks named `finance-capture`, `finance-balances`, or `finance-capture-manager` for capture, balances, or queue management. Each note can host its own independent panel.

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

После проверки и добавления плагина в каталог:

1. В Obsidian откройте **Настройки → Сторонние плагины → Обзор**, найдите **Finance Capture**, нажмите **Установить**, затем включите плагин.
2. В настройках Finance Capture задайте имя автора, корневую папку синхронизации внутри хранилища и подпапку карточек операций.
3. Настройте Syncthing так, чтобы эта папка синхронизировалась с папкой Finance на компьютере. Запущенное desktop-приложение импортирует очередь и передаёт на телефон счета и справочники.

Для бета-тестирования до появления плагина в каталоге установите **BRAT**, выберите **Add beta plugin** и укажите `gmdveast/finance-capture`.

Для создания операции нужен хотя бы один синхронизированный активный счёт. Finance desktop — единственный компонент, который записывает данные в Excel; версия плагина не зависит от версии desktop.

## Панели и команды

Откройте палитру команд Obsidian и выберите **Добавить финансовую операцию** для быстрого ввода. Вставьте в заметку блок кода `finance-capture`, `finance-balances` или `finance-capture-manager`, чтобы добавить независимую панель ввода, балансов или управления очередью.

Редактирование созданной карточки не меняет JSON операции. Удаление связанной ожидающей карточки при работающем плагине может отменить операцию в очереди. Архивная карточка означает отсутствие JSON в очереди; импорт подтверждается только соответствующей квитанцией. Очистка очереди требует подтверждения и затрагивает только файлы, созданные плагином.

## Конфиденциальность и совместимость

Плагин использует API хранилища Obsidian, работает на телефоне и компьютере, не выполняет сетевых запросов, не собирает телеметрию и не обращается к файлам вне хранилища. Syncthing — отдельное приложение: настроенные устройства получают синхронизируемые финансовые данные. Установкой и обновлением управляет Obsidian; для бета-тестирования можно использовать BRAT. Версия плагина не зависит от версии desktop.

Файлы релиза — `main.js`, `manifest.json` и `styles.css`; отдельная сборка не требуется. Лицензия: [MIT](LICENSE).
