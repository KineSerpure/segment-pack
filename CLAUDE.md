# segment-pack — публичный репозиторий сборки SEGMENT

- `credits.json` — авторы и разработчики для лаунчера (Настройки → Лаунчер). Формат: `{"groups":[{"title":"...","people":[{"name":"...","role":"..."}]}]}`.
- `news.json` — новости лаунчера (`{"news":[{"title","date","author","image","text"}],"notice":{...}}`), правятся на GitHub без релиза; если поле есть, оно заменяет новости/notice из pack.json.
- `info/` — раздел «Информация»: `seasons.json` (`{"seasons":[{season,current?,articles:[как новости + fields]}]}`, актуальный по умолчанию — последний), `persons.json` (`{"persons":[{name,role,show:"skin"|"image",skin|nick,model,image,fields,text}]}`), `other.json` (`{"other":[как новости + fields]}`). `fields` — `[["Поле","значение"]]`. Пути `skins/…`, `images/…` — от папки `info/`. Файл может быть и просто списком.
- `release/` — файлы текущей версии сборки из packtool (`pack.json`, `overrides.zip`, моды не с CurseForge) и `NOTES.md`. Push в main → workflow создаёт релиз `v<version из pack.json>` и делает его последним; лаунчер берёт `releases/latest/download/pack.json`.
- Новая версия: поднять `version` (packtool -version), заменить всё содержимое `release/`, push.
- Моды с лицензией «All Rights Reserved» — только с разрешения автора.
