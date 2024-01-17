# Player Animations

For animations, you should first change the player's model, see the previous chapter.
First of all, there are two main animation modes: Single and Looping.
You can find the names of animations with the command `/hollowengine model <path to the model>` (hints are available).

## Single Animations

To play an animation once, you need a simple command.

!!! note "Template"

    ```kotlin
    player playOnce { "animationName" }
    ```

## Looping Animations

### Start

!!! note "Plays a looping animation (endlessly) | Template"

    ```kotlin
    player playLooped { "animationName" }
    ```

### Stop

!!! note "Stops playing the looping animation | Template"

    ```kotlin
    player stop { "animationName" }
    ```

## Animation Configuration

If these settings are not enough or the animation is not playing as you want, you probably need this mode:

!!! note "Detailed animation playback configuration | Templates"
```kotlin
player play {
animation = "animationName" // Animation name
layerMode = LayerMode.ADD // Animation layering mode. Options: ADD - add another animation to the current position. OVERWRITE - completely overwrite other animations.
playType = PlayMode.ONCE // Animation playback mode. Options: ONCE - once, LOOPED - looping, LAST_FRAME - stop at the last frame, REVERSED - looping, but in reverse after completion
speed = 1f // Animation speed
}
```

---
