# Автоматический запуск скрипта.

!!! danger "Напоминаю"

    > Скрипты этой категории `Script - MOD` - пишутся в `.mod.kts`!

---

!!! note "Вы сможете указать какой скрипт запускать, когда игрок заходит в мир"

    > Работать будет только при первом заходе в мир.

    ```kotlin
    import dev.ftb.mods.ftbteams.FTBTeamsAPI
    import net.minecraft.server.level.ServerPlayer
    import net.minecraft.stats.Stats
    import net.minecraftforge.event.entity.player.PlayerEvent.PlayerLoggedInEvent
    import ru.hollowhorizon.hollowengine.common.files.DirectoryManager.fromReadablePath
    import ru.hollowhorizon.hollowengine.common.scripting.story.runScript
    // Всё что выше, это импорты нужных библиотек. Они обязательны!
    
    fun onPlayerJoin(event: PlayerLoggedInEvent) { // Функция - Когда игрок подключаемя к миру
            val player = event.entity as ServerPlayer // Создаём переменную Игрок
            if(player.stats.getValue(Stats.CUSTOM.get(Stats.PLAY_TIME)) == 0) {
                runScript(player.server, FTBTeamsAPI.getPlayerTeam(player), "<path/to/  script>".fromReadablePath()) // ЗАпускаем указанный скрипт
            }
        }
        
    FORGE_BUS.register(::onPlayerJoin)
    ```
    
    - `path/to/script` - Укажите путь до скрипта.
:::

---
