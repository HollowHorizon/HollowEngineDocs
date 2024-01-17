# Character Animations

First of all, there are 2 main animation modes: Single and Looping.
You can find the names of animations using the command `/hollowengine model <model path>` (hints are available).

## Single Animations

To play an animation once, a simple command is enough.

!!!note "Template"
```kotlin
npc playOnce { "animationName" }
```

## Looping Animations

### Start

!!!note "Plays a looping animation (infinitely) | Template"
```kotlin
npc playLooped { "animationName" }
```

### Stop

!!!note "Stops playing a looping animation | Template"
```kotlin
npc stop { "animationName" }
```

## Animation Configuration

If these settings are not enough for you or the animation is not playing as you want, you probably need this mode:

!!!note "Fine-tune animation playback | Templates"
```kotlin
npc play {
animation = "animationName" // Animation name
layerMode = LayerMode.ADD // Animation layering mode. Options: ADD - add another animation to the current position. OVERWRITE - completely overwrite other animations.
playType = PlayMode.ONCE // Animation playback mode. Options: ONCE - once, LOOPED - in a loop, LAST_FRAME - stop on the last frame, REVERSED - in a loop, but in reverse after completion.
speed = 1f // Animation speed
}
```


---
