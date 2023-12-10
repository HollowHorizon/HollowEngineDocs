# Спавн NPC

## Шаблон

!!! info "Шаблон для спавна NPC"

    ```kotlin
    val <npcID> by NPCEntity.creating{
    	settings = NPCSettings("<nick>", "<model>",   <attributes>, <hitboxSize>, <showMick>)
    	location = SpawnLocation("<dimension>", pos(<x>, <y>, <z>), vec(<pitch>, <yaw>))
    }
    ```
    
    - Обозначения:
    > - `npcID` - Уникальный ID для вашего NPC. Через него вы, обращаетесь к конкретному NPC. 
    > - `nick` - Имя NPC.  
    > - `model` - Укажите путь до модели. Путь должен начинаться с `modID:`
    > - `attributes` - Аттрибуты для NPC, по типу: Здоровье, скорость и т.д. 
    > - `size` - Размер хитбокса NPC -> `Pair(float1, float2)`
    >   - `float1` - Ширина. 
    >   - `float2` - Высота. 
    > - `showNick` - Отображение `displayName` над головой NPC. 
    >   - `false` - не отображать, 
    >   - `true` - отображать. 
    > - `dimension` - Измерение, в котором будет спавниться NPC. Указывать надо сначала с `modID`, пример: `    minecraft:overworld`. 
    > - `pos(x, y, z)` - Позиция спавна NPC. 
    > - `vec(pitch, yaw)` - Углы поворота при спавне NPC. 

    - Необязательные значения:
    > - `attributes`. 
    > - `Pair(),` 
    > - `showNick`. 

---

## Базовый NPC

!!! info "Для спавна базового NPC, оставь поле `NPCSettings()` - пустым"

    Вот пример, как должен выгдядеть скрипт спавна "Базового NPC":

    ```kotlin
    val npc by NPCEntity.creating{
        // settings = NPCSettings() - не нужен для Базового NPC
        location = SpawnLocation("minecraft:overworld", pos(0, -58, 0))
    }
    ```
![Спавн базового NPC](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/spawn-basic-npc.gif)

---

## Кастомный NPC

!!! info "Основым нужно, чтобы ты указал путь к модели"

    ```kotlin
    val npc by NPCEntity.creating{
        settings = NPCSettings("Виталик 2", "hollowengine:models/entity/temp2.gltf")
        location = SpawnLocation("minecraft:overworld", pos(0, -58, 0))
    }
    ```
![Спавн кастомного NPC](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/spawn-custom-npc.gif)

---

### Аттрибуты

!!! info "Все существующие аттрибуты, вы можете узнать через команду `/attribute`"

    От вас лишь требуется указать, там где `attributes`, это:
    
    ```kotlin
    Attributes("<attributeName>" to <float>)
    ```
    > Обозначения: 
    > - `attributeName` - название аттрибута. 
    > - `float` - Число/Цифра, где в конце стоит `f`, пример: `10f`

---
