# Particles

Note: Not all parameters are listed here; it is recommended to familiarize yourself with the [HollowParticleBuilder](https://github.com/HollowHorizon/HollowCore/blob/1.19.2/src/main/java/ru/hollowhorizon/hc/client/render/particles/HollowParticleBuilder.kt) class.

HollowEngine provides a set of tools for creating particles. To enter the space for creating and configuring particles, type:
```kts
particles {
    // Your settings will go here
}
```

## Parameters of the `particles` Method

The parameters themselves are quite numerous:
- world (variable) - the dimension where the particles will spawn, for example `"minecraft:overworld"`.
- particle (variable) - сама частица, напримерthe particle itself, for example:: `"hc:star"` or `"hc:circle"`. Currently, these are all types of particles; later, how to add your own will be described here.
- settings (method) - the space for particle settings. More details below.

## Parameters of the `settings` method

### Random Motion

- `randomMotion(xSpeed: Double, ySpeed: Double, zSpeed: Double)` - random motion along three axes.
- `randomMotion(horizontalSpeed: Double, verticalSpeed: Double)` - random motion horizontally and vertically.
- `randomMotion(speed: Double)` - random motion along all three coordinate axes.

### Random Offset

- `randomOffset(x: Float, y: Float, z: Float)` - random offset along three axes from 0 to the specified values.
- `randomMotion(horizontalSpeed: Float, verticalSpeed: Float)` - random offset horizontally and vertically.
- `randomMotion(speed: Float)` - random offset along all three coordinate axes.

### Rotation

- `spin(startValue: Float, endValue: Float)` - particle rotation from the initial position to the final one over the entire particle's lifetime.
- `spin(startValue: Float, middleValue: Float, endValue: Float)` - similar, but with 3 values.

Parameters by name
- `startToMiddleEasing = Interpolation.LINEAR` - [interpolation](../../common/util/interpolations) from the start to the middle of the rotation.
- `middleToEndEasing = Interpolation.LINEAR` - [interpolation](../../common/util/interpolations) from the middle to the end of the rotation.

### Color

- `color(r1: Float, g1: Float, b1: Float, r2: Float, g2: Float, b2: Float)` - initial and final color of the particle, specified in [RGB procentages](https://keiwando.com/color-picker/) from `0f` to `1f`.

Parameters by name
- `colorCurveEasing = Interpolation.LINEAR` - [interpolation](../../common/util/interpolations) from the initial color to the final one.

### Transparency

Note: Transparency towards the end of the particle's life does not currently work.

- `transparency(startValue: Float, endValue: Float)` - transparency of the particle from the initial position to the final one over the entire particle's lifetime.
- `transparency(startValue: Float, middleValue: Float, endValue: Float)` - similar, but with 3 values.

Parameters by name
- `startToMiddleEasing = Interpolation.LINEAR` - [interpolation](../../common/util/interpolations) from the start value to the middle value.
- `middleToEndEasing = Interpolation.LINEAR` - [interpolation](../../common/util/interpolations) from the middle value to the end value.

### Gravity

- `gravity: Float = 0.1f` - gravitational force on the particle.

### No Clip

- `noClip = true / false` - whether the particle can pass through blocks.

### Sprite Change Type

- `spritePicker` (variable) - type of sprite change for the particle.

Allowed options
- SpritePicker.FIRST_INDEX - the first image from the sprite list.
- SpritePicker.LAST_INDEX - the last image from the sprite list.
- SpritePicker.WITH_AGE - The image changes depending on the particle's lifetime.
- SpritePicker.RANDOM_SPRITE - a random image from the sprite list.

### Particle Lifetime

- `lifetime: Int` (variable) - particle lifetime. (in ticks)

## Particle Spawning

- `spawn(x: Double, y: Double, z: Double)` - spawn 1 particle at the specified coordinates.
- `repeat(x: Double, y: Double, z: Double, n: Int)` - spawn `n` particles at the specified coordinates.

## Пример

```kts
particles {
    particle = "hc:star"
    settings {
        randomOffset(0.05, 0.05) // Random offset
        randomMotion(0.05) // Random motion direction
        lifetime = 100 // Lifetime of one particle
        gravity = 0.1f // Particle gravity

        spawn(x, y, z)
    }
}
```