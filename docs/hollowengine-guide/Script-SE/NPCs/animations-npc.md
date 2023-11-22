# Анимации у NPC

## Once

!!! note "Воспроизводит анимацию 1 раз | Шаблон"

    ```kotlin
    <npcID> playOnce { "<animationName>" }
    ```

## Looped

!!! note "Воспроизводит анимацию в цикле(бесконечно) | Шаблон"

    ```kotlin
    <npcID> playLooped { "<animationName>" }
    ```

## Stop

!!! note "Останавливает воспроизведение анимации | Шаблон"

    ```kotlin
    <npcID> stop { <active_animationName> }
    ```

## Animation Setting

!!! note "Настрой воспроизведение анимации детально | Шаблоны"

    ```kotlin
    <npcID>.play {"<animationName>", <playType>, priority = <float>, <speed>}
    ```
    
    - Обозначения: 
    > - `animationName` - Название анимации в модели. 
    > - `playType` - В каком режиме проигрывать анимацию. [Ниже написано]. 
    > - `priority = <float>` - Приоритет к анимации. 
    > - `speed` - Скорость анимации. 

### PlayTypes

> - playType = PlayType.ONCE | Воспроизводит 1 раз. 
> - plaType = PlayType.LOOPED | Воспроизводит в цикле(бесконечно). 
> - playType = PlayType.LAST_FRAME | Воспроизводит 1 раз, после застывает на последнем кадре. 
> - playType = PlayType.REVERSED | Воспроизводит сначала в одну сторону(вперёд), после в другую(назад) 1 раз. 

---
