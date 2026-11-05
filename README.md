# onyx — релизы Android-приложения

Здесь лежат готовые APK приложения **onyx** — электронного дневника для «Сетевого города».

**Скачать последнюю версию:** [onyx.apk](https://github.com/MrNeoner/onyx-releases/releases/latest/download/onyx.apk) · все версии — во вкладке [Releases](https://github.com/MrNeoner/onyx-releases/releases).

- Android 7 и новее, бесплатно.
- С версии 1.2 приложение обновляется само: при выходе новой версии появится «Вышла новая версия» → «Обновить» (или карточка в «Настройках») — APK скачивается, проверяется и ставится поверх.
- Все версии подписаны одним ключом (SHA-256 сертификата `b62a032b2f01157ac185f69af322912c41307d53e179d8b6f434c447f51253d5`), поэтому ставятся поверх без потери данных.
- Сайт: [onyxdiary.vercel.app](https://onyxdiary.vercel.app) · вопросы — в Telegram [@mrneoner](https://t.me/mrneoner).

## Как выпускается версия

1. Собрать и подписать APK, посчитать SHA-256 и размер.
2. Обновить `release.json`: `tag`, `version`, `versionCode`, `sha256`, `size`, `notes` и `sources` — ссылки, откуда workflow скачает APK.
3. Workflow `publish` скачивает APK, проверяет SHA-256, размер, подпись и versionCode и публикует релиз с файлом `onyx.apk`. В описание добавляется скрытая строка `<!-- onyx:{"versionCode":…,"sha256":"…"} -->` — по ней сервер onyx и приложение проверяют обновление.

Сервер onyx берёт последний релиз отсюда (кэш 10 минут).
