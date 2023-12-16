# Спавн NPC

## Шаблон

!!! info "Шаблон для спавна NPC"

    Этот шаблон вкл в себя все параметры, которые поддерживаются при создании НПС:

    ```kotlin
    val <npcID> by NPCEntity.creating{
    	name = "<text>" // Ник НПС
        model = "<path/to/model>" // Путь до модели. В начале пишется modID, а после уже сам путь
        Attributes("<attribute>" to <float>) // Атрибуты
        size = <width> to <height> // Размер хитбокса
        showName = <false/true> // Отображение Ника НПС над его головой
        transform = Transform{} // Изменить Отображение модели по: Смещение, поворот, размер
        animation[AnimationType.<defaultAnimationID>] = "<newAnimationName>" // Замена дефолтной анимации на свою(кастомную, другую)
        world = "<worldID>" // Измерение спанва
        pos = pos(<x>, <y>, <z>) // Пизиция спавна. Либо все значения это int, либо все значения это double
        rotation = vec(<pitch>, <yaw>) // Поворот головы
    }
    ```

---

## Базовый NPC

!!! info "Для спавна базового NPC, укажите максимум только кноординаты спавна"

    Вот пример, как должен выгдядеть скрипт спавна "Базового NPC":

    ```kotlin
    val npc by NPCEntity.creating{
        pos = pos(0, -57, 0) // Если будет pos(<int>, <double>, <int>) - работать не будет
    }
    ```
![Спавн базового NPC](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/spawn-basic-npc.gif)

---

## Кастомный NPC

!!! info "Основым нужно, чтобы ты, как минимум, указан имя НПС, путь к модели и при необходимости путь к текстуре для модели"

    ```kotlin
    val npc by NPCEntity.creating{
        name = "Вася"
        model = "hollowengine:/template/better_temp.gltf"
        textures["better_texture"] = "textures:character/human_1.png"
    }
    ```
![Спавн кастомного NPC](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/spawn-custom-npc.gif)

---

### Аттрибуты

!!! info "Все существующие аттрибуты, вы можете узнать через команду `/attribute <кому>`"

    От вас лишь требуется указать, там где `attributes`, это:
    
    ```kotlin
    Attributes("<attributeName>" to <float>)
    ```
    > Обозначения: 
    > - `attributeName` - название аттрибута. 
    > - `float` - Число/Цифра, где в конце стоит `f`, пример: `10f`

---
