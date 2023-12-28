# Настройка персонажа

Помимо базовой настройки при спавне вы также можете в процессе скрипта менять разные параметры нпс, например: модель, текстуру, стандартные анимации, смещение, поворот и размеры.

```kts
npc configure {
    model = "hollowengine:models/entity/player_model.gltf" // Замена модели персонажа. Указывается в формате ResourceLocation
    animations[AnimationType.IDLE] = "animationName" // Замена стандартных анимаций персонажа. Названия всех анимаций можно посмотреть командой /hollowengine model <модель>
    textures["original_name"] = "hollowengine:textures/skins/my_skin.png" // Замена стандартной текстуры. Названия оригинальных текстур можно посмотреть командой /hollowengine model <модель>. Сами текстуры указываются в формате ResourceLocation.
    transform = Transform( //Параметры модели: перемещение, поворот и масштаб
      tX=1.5f //сдвинем нашу модель на 1.5 блока по x.
    )
}
```