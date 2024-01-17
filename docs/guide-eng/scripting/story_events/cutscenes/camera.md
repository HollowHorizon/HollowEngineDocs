# Camera Control

To control the camera, there is a corresponding item: `Camera`. You can find it in the creative inventory.

## Setup

It adds a new point on the right mouse button click and removes the nearest point to the player on the left mouse button click. You can also rotate the camera clockwise and counterclockwise by pressing `+` and `-` (Press `c` to reset).

To save the result, press `Shift + Right Mouse Button`, and a new file with the result will appear at the path `.minecraft/hollowengine/camera/`.

## Launch

Example:

```kotlin
camera {
    time = 10.sec // Camera flight time
    path = "123456.nbt" // File name in the camera folder
    interpolation = Interpolation.LINEAR // Interpolation (slowing down at the beginning and end)
}
```

All types of interpolations can be found [here](/common/util/interpolations).