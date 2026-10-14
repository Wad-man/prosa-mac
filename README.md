# ProsaMD для macOS

Минималистичный открытый редактор и читалка Markdown — «блокнот» для `.md`-файлов. Это **отдельная macOS-версия** [ProsaMD](https://github.com/Wad-man/prosa): с 2026-10-14 платформенные линии разделены (#121), ядро синхронизируется из основного репозитория (правки общего кода принимаются там — «сначала upstream»).

- Основной репозиторий (Windows/Linux, обсуждения, roadmap): **[Wad-man/prosa](https://github.com/Wad-man/prosa)**
- Сайт: **[prosamd.ru](https://prosamd.ru)**

## Установка

Универсальная сборка (Intel + Apple Silicon) — `*.dmg` из [релизов](https://github.com/Wad-man/prosa-mac/releases).

Сборка не подписана Apple Developer ID: первый запуск — ПКМ по ProsaMD.app → «Открыть» → «Открыть», либо снять карантин в Терминале:

```sh
xattr -cr /Applications/ProsaMD.app
```

Обновления приходят из окна «О программе» (клик по версии в статусной строке) — канал обновлений mac-версии: этот репозиторий. Версии имеют суффикс `-mac.N` и наследуют номер ядра (`0.2.0-rc.7-mac.1` = ядро rc.7 + первая mac-сборка).

## Разработка

```sh
npm install
npm run tauri dev
```

Требуется Xcode Command Line Tools. Флаг `prosa_mac` (компилирует mac-модули — нативное меню, watchdog) ставится автоматически через `src-tauri/.cargo/config.toml`.

Ответственные за mac-часть модули: `src-tauri/src/menu.rs`, `src-tauri/src/watchdog.rs` (checker), подключение — за `cfg(prosa_mac)` в `src-tauri/src/lib.rs`.

## Лицензия

MIT (как у основного репозитория).
