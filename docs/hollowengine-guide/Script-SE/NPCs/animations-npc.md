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
    <npcID>.play {
        animation = "<animationName>" // Название анимации
        layerMode = LayerMode.<modeType> // Режим проигрывания. Есть:
        // - LayerMode.ADD - Умножить
        // - LayerMode.OVERWRITE - Перезаписать
        playType = PlayMode.<playType> // Как проигрывать анимацию. Есть:
        // - PlayMode.ONCE - 1 раз
        // - PlayType.LOOPED - в цикле
        // - PlayTyp.LAST_FRAME - Зависнуть на последнем кадре
        // - PlayMode.REVERSED - в цикле вперёд и обратно
        speed = <float> // Скорость анимации
    }
    ``` 

---
