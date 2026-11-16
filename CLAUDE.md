# segment-pack — публичный репозиторий сборки SEGMENT

- `credits.json` — авторы и разработчики для лаунчера (Настройки → Лаунчер). Формат: `{"groups":[{"title":"...","people":[{"name":"...","role":"..."}]}]}`.
- `release/` — файлы текущей версии сборки из packtool (`pack.json`, `overrides.zip`, моды не с CurseForge) и `NOTES.md`. Push в main → workflow создаёт релиз `v<version из pack.json>` и делает его последним; лаунчер берёт `releases/latest/download/pack.json`.
- Новая версия: поднять `version` (packtool -version), заменить всё содержимое `release/`, push.
- Моды с лицензией «All Rights Reserved» — только с разрешения автора.
