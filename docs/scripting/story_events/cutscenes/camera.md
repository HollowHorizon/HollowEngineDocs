Для управления камерой есть соответствующий предмет: `Камера`. Найти вы его можете в вкладке креатива.

## Настройка

На правую кнопку мыши она добавляет новую точку, а на левую кнопку удаляет ближайшую точку к игроку.
Также нажимая `+` и `-` вы можете поворачивать камеру по часовой и против часовой стрелки. (Для сброса нажмите `c`)

Чтобы сохранить результат нажмите `shift + правая кнопка мыши`, после чего по пути `.minecraft/hollowengine/camera/` появится новый файл с результатом.

## Запуск

Пример:

```kotlin
camera {
    time = 10.sec //время пролёта камеры
    path = "123456.nbt" //название файла в папке камеры
    interpolation = Interpolation.LINEAR //Интерполяция (замедление в начале и конце)
}
```

Все виды интерполяций есть [тут](https://github.com/HollowHorizon/HollowCore/blob/1.19.2/src/main/java/ru/hollowhorizon/hc/client/utils/math/Interpolation.kt).