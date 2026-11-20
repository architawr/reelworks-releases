# ReelWorks — релизы

Публичные файлы для ReelWorks.app. Исходный код приложения — в закрытом репозитории; здесь только то,
что скачивает само приложение или человек при установке.

- **Релизы `vX.Y.Z`** — обновления кода приложения (`reelworks-app-<версия>.tar.gz` и `latest.json`, подписанный ed25519)
  и установщик `ReelWorks-<версия>-arm64.dmg`. Приложение проверяет подпись и сумму перед установкой обновления.
- **Пререлиз `components`** — программы, которых нет в .dmg: приложение докачивает их фоном после установки.
  Файлы не меняются: в имени — начало sha256, полные суммы закреплены в коде приложения, файл с другой суммой оно не примет.
  - `ffmpeg-*`, `ffprobe-*` — статическая сборка FFmpeg для Apple Silicon от https://ffmpeg.martin-riedl.de,
    лицензия GPL v3 (`--enable-gpl --enable-version3`). Исходный код FFmpeg — https://ffmpeg.org/download.html.
  - `whisper-cli-*` — whisper.cpp (лицензия MIT), статическая сборка для Apple Silicon из тега
    https://github.com/ggml-org/whisper.cpp — распознавание речи для голосового ввода.
  Модель распознавания речи (`ggml-small-q5_1.bin`) скачивается напрямую у авторов whisper.cpp с Hugging Face.

---

Public files for ReelWorks.app: signed app-code updates and installers (`vX.Y.Z` releases) and the programs the app
downloads after installation (`components` pre-release: FFmpeg — GPL v3, sources at ffmpeg.org; whisper.cpp — MIT).
