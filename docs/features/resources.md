# Загрузчик ресурсов

HollowEngine предоставляет свой загрузчик ресурсов. Прежде всего **каждый мод имеет свой набор ресурсов** и каждый из этих наборов делится на **клиентские** и **серверные** ресурсы.
Используя данный загрузчик ресурсов вы можете добавлять свои ресурсы в HollowEngine и другие моды.

## Клиентские ресурсы

Клиентские ресурсы - это ресурсы, которые применяются только на клиентах. Это в первую очередь: модели, текстуры, звуки, переводы и т.п. <br>
Если проще, то это простые ресурспаки, которые добавятся в любом случае.

Чтобы добавить свои ресурсы вам необходимо положить их по пути: `.minecraft/hollowengine/assets/<modid>/<path>/`, где: <br>
・ `<modid>` - id мода, в который вы хотите добавить ресурс, например: `hollowengine`. <br>
・ `<path>` - путь к файлу, который вы хотите добавить, например: `models/entities/`. <br>

Например Вы можете хранить ваши модели персонажей по такому пути: `.minecraft/hollowengine/assets/hollowengine/models/entities/`.

После изменения ресурсов необходимо нажать F3+T, чтобы перезагрузить клиентские ресурсы.

## Серверные ресурсы

Серверные ресурсы - это ресурсы, которые хранятся только на сервере, например рецепты, таблицы лута, структуры и т.п. 
Если проще, то это датапаки, которые будут загружены при входе в мир.

Чтобы добавить свои ресурсы вам необходимо положить их по пути: `.minecraft/hollowengine/data/<modid>/<path>/`, где: <br>
・ `<modid>` - id мода, в который вы хотите добавить ресурс, например: `hollowengine`. <br>
・ `<path>` - путь к файлу, который вы хотите добавить, например: `recipes`. <br>

Например, Вы можете хранить ваши рецепты датапака по такому пути: `.minecraft/hollowengine/data/hollowengine/recipes/`.

После изменения данных необходимо прописать `/reload`, чтобы перезагрузить серверные ресурсы.

## Resource Location

Resource Location - способ записи пути к файлу мода внутри кода.

Предположим вы положили файл `my_cool_model.gltf` по пути `.minecraft/hollowengine/assets/my_super_mod/models/entities/`, тогда Resource Location необходимо записать так: `"my_super_mod:models/entities/my_cool_model.gltf"`, чтобы двоеточие разделяло мод и относительный путь.