# segment-pack — публичный репозиторий сборки SEGMENT

- `credits.json` — авторы и разработчики для лаунчера (Настройки → Лаунчер). Формат: `{"groups":[{"title":"...","people":[{"name":"...","role":"..."}]}]}`.
- `news.json` — новости лаунчера (`{"news":[{"title","date","author","image","text"}],"notice":{...}}`), правятся на GitHub без релиза; если поле есть, оно заменяет новости/notice из pack.json.
- `servers.json` — `{"servers":[{"name","address"}]}` (домен или IP:порт), серверы для автоподключения; пустой список — настройка в лаунчере серая.
- `info/` — раздел «Информация»: `seasons.json` (`{"seasons":[{season,current?,articles:[как новости + fields]}]}`, актуальный по умолчанию — последний), `persons.json` (`{"persons":[{name,role,show:"skin"|"image",skin|nick,arms:"толстые"|"тонкие" (или model),image,fields,text}]}`), `other.json` (`{"other":[как новости + fields]}`). `fields` — `[["Поле","значение"]]`. Пути `skins/…`, `images/…` — от папки `info/`. Файл может быть и просто списком.
- `launcher.json` — последняя версия лаунчера игроков (`version`, `url` на `Launcher.exe` в релизе `launcher-v<версия>`, `sha1`, `size`, `notes`, `date`, `required`). Пишет Админ Лаунчер (экран «Лаунчер»); релизы `launcher-v*` создаются НЕ последними, чтобы `releases/latest` оставался релизом сборки.
- `files/`, `info/files/` — файлы для кнопок «скачать файл» и видео mp4 в записях (загружает Админ Лаунчер).
- `media/` — дополнительные музыкальные темы лаунчера (не вшиты в exe; лаунчер качает их один раз и сверяет SHA-1 со списком `remote.json` внутри exe). Файлы не менять и не удалять — у игроков сломается музыка; новая тема — новый файл + новая версия лаунчера.
- `release/` — файлы текущей версии сборки из packtool (`pack.json`, `overrides.zip`, моды не с CurseForge) и `NOTES.md`. Push в main → workflow создаёт релиз `v<version из pack.json>` и делает его последним; лаунчер берёт `releases/latest/download/pack.json`.
- Новая версия: поднять `version` (packtool -version), заменить всё содержимое `release/`, push.
- Моды с лицензией «All Rights Reserved» — только с разрешения автора.
