# Туториал №2

!!! note "Создадим путь для перемещения камеры, состоящий из 3-х точек, Длительность пути будет 10 сек и установим интерполяцию `SINE_IN_OUT`"
    ```kotlin
    createCameraPath {
        spline(10.sec,
            vec(-180f, 0f), vec(-150f, -10f),
            pos(120.34, 64, -12.53),
            pos(130.43, 65, -23.65),
            pos(100.23, 67, -34.32),
            interpolation = Interpolation.SINE_IN_OUT
        )
    }
    ```

---
