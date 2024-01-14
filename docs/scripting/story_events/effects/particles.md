# Частицы

Примечание: здесь указаны не все параметры, рекомендуем ознакомиться с классом [HollowParticleBuilder](https://github.com/HollowHorizon/HollowCore/blob/1.19.2/src/main/java/ru/hollowhorizon/hc/client/render/particles/HollowParticleBuilder.kt).

HollowEngine предоставляет некоторый набор инструментов для создания частиц.
Чтобы перейти в пространсво создания и настройки частиц введите:
```kts
particles {
    //Тут будут ваши настройки
}
```

## Параметры метода `particles`

Самих параметров тут прилично
- world (переменная) - измерение, где заспавнить частицы, например `"minecraft:overworld"`.
- particle (переменная) - сама частица, например: `"hc:star"` или `"hc:circle"`. На данный момент это все виды частиц, позднее здесь будет расписано, как можно добавить свои.
- settings (метод) - пространство настройки частиц. Подробнее ниже.

## Параметры метода `settings`

### Случайное направление

- `randomMotion(xSpeed: Double, ySpeed: Double, zSpeed: Double)` - случайное направление по трём осям.
- `randomMotion(horizontalSpeed: Double, verticalSpeed: Double)` - случайное направление по горизонтали и вертикали.
- `randomMotion(speed: Double)` - случайное направление сразу по трём осям координат.

### Случайное смещение

- `randomOffset(x: Float, y: Float, z: Float)` - случайное смещение по трём осям от 0 до указанного.
- `randomMotion(horizontalSpeed: Float, verticalSpeed: Float)` - случайное смещение по горизонтали и вертикали.
- `randomMotion(speed: Float)` - случайное смещение сразу по трём осям координат.

### Поворот

- `spin(startValue: Float, endValue: Float)` - поворот частицы от начального положения к конечному на протяжении всего времени жизни частицы.
- `spin(startValue: Float, middleValue: Float, endValue: Float)` - аналогично, но с 3 значениями.

Параметры по имени
- `startToMiddleEasing = Interpolation.LINEAR` - [интерполяция](../../common/util/interpolations) от начала к середине поворота.
- `middleToEndEasing = Interpolation.LINEAR` - [интерполяция](../../common/util/interpolations) от середины к концу поворота.

### Цвет

- `color(r1: Float, g1: Float, b1: Float, r2: Float, g2: Float, b2: Float)` - начальный и конечный цвет частицы, указывается в [процентах RGB](https://keiwando.com/color-picker/) от `0f` до `1f`.

Параметры по имени
- `colorCurveEasing = Interpolation.LINEAR` - [интерполяция](../../common/util/interpolations) от начального цвета к конечному.

### Прозрачность

Примечание: прозрачность к концу жизни частицы временно не работает.

- `transparency(startValue: Float, endValue: Float)` - прозрачность частицы от начального положения к конечному на протяжении всего времени жизни частицы.
- `transparency(startValue: Float, middleValue: Float, endValue: Float)` - аналогично, но с 3 значениями.

Параметры по имени
- `startToMiddleEasing = Interpolation.LINEAR` - [интерполяция](../../common/util/interpolations) от начального значения к среднему значению.
- `middleToEndEasing = Interpolation.LINEAR` - [интерполяция](../../common/util/interpolations) от среднего значения к конечному значению.

### Гравитация

- `gravity: Float = 0.1f` - сила тяжести на частицу. 

### No Clip

- `noClip = true / false` - может ли частица проходить сквозь блоки.

### Тип смены спрайтов

- `spritePicker` (переменная) - тип смены картинок партикла.

Допустимые варианты
- SpritePicker.FIRST_INDEX - первая картинка из списка спрайтов.
- SpritePicker.LAST_INDEX - последняя картинка из списка спрайтов.
- SpritePicker.WITH_AGE - Картинка меняется в зависимости от времени жизни частицы.
- SpritePicker.RANDOM_SPRITE - случайная картинка из списка спрайтов.

### Время жизни частицы

- `lifetime: Int` (переменная) - время жизни частицы. (в тиках)

## Запуск партиклов

- `spawn(x: Double, y: Double, z: Double)` - заспавнить 1 частицу на указанных координатах.
- `repeat(x: Double, y: Double, z: Double, n: Int)` - заспавнить `n` частиц на указанных координатах.

## Пример

```kts
particles {
    particle = "hc:star"
    settings {
        randomOffset(0.05, 0.05) // Случайное смещение
        randomMotion(0.05) // Случайное направление движения
        lifetime = 100 // Время жизни одной частицы
        gravity = 0.1f // Гравитация частицы

        spawn(x, y, z)
    }
}
```