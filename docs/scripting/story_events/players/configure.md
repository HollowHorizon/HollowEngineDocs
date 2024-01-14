# Изменение моделей игроков

Чтобы изменить модель игроку вам в первую очередь нужно получить нужного игрока из команды:

```kotlin
val player by team[{ "Ник Игрока" }]
```

Теперь вы можете его настроить.

```kotlin
player configure {
    model = "hollowengine:models/entity/player_model.gltf" // Замена модели игрока. Указывается в формате ResourceLocation
    animations[AnimationType.IDLE] = "animationName" // Замена стандартных анимаций персонажа. Названия всех анимаций можно посмотреть командой /hollowengine model <модель>
    textures["original_name"] = "hollowengine:textures/skins/my_skin.png" // Замена стандартной текстуры. Названия оригинальных текстур можно посмотреть командой /hollowengine model <модель>. Сами текстуры указываются в формате ResourceLocation.
    transform = Transform( //Параметры модели: перемещение, поворот и масштаб
        tX=1.5f //сдвинем нашу модель на 1.5 блока по x.
    )
}
```

Путь к модели указывается, в формате [ResourceLocation](../../../../features/resources).

!!! note "Вернуть игрока обратно."
    Чтобы вернуть стандартную модель игрока, просто укажите вместо модели строку `"%NO_MODEL%"`.