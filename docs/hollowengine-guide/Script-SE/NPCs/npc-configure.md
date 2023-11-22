# Конфигурация NPC

!!! info "Всё перечисленное здесь, пишется..."
    ```kotlin
    <npcID>.configure {
        // т.е. здесь!
    }
    ```

## Установке текстуры / скина

!!! note "Установить новую текстуру"
    ```kotlin
        textures["<texture>"] = "<path/to/new_texture>" // Заменяем текущую текстуру на навую
    ```
    > Обозначения: 
    > - `texture` - Имя текстуры, которая сейчас на модели. 
    > - `<path/to/new_texture>` - Путь к новой текстуре. Начинаться должен с `<modID>:`. 
    > - `modID` - `ID` мода. 
---

!!! note "Установить новый скин"
    ```kotlin
        textures["<texture>"] - skin("<nickname>") // Работает только с ОФИЦИАЛЬНЫМИ скинами Mojang. Вводите корректно имя, иначе -> краш
    ```
    > Обозначения: 
    > - `texture` - Имя текстуры, которая сейчас на модели. 
    > - `nickname` - Ник игрока, у которого есть лицензия. 

---

## Установка стандартных анимаций

!!! note "Замени стандартную анимацию"
    ```kotlin
        animation[AnimationType.<type>] = "<new_animationName>" // Замена стандартной анимации на новую
    ```
    > Обозначения: 
    > - `type` - [Тип анимации](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/Tools/standartAnimationType). 
    > - `new_animationName` - Название анимации. 

---
