# Timers and Waits

Often, you may need to pause a script until a certain event occurs. This section covers most of the triggers you might need.

## Wait for Time

In this case, you can pause the script for several seconds, minutes, or even hours.

!!! info "Template"
```kts
wait { <time> }
```
Replace `<time>` with a number:
> - `Int` - time in ticks.
> - `Int.sec` - time in seconds.
> - `Int.min` - time in minutes.
> - `Int.hour` - time in hours.
> ---
> You can also add time using `+`, for example, wait for 10 minutes and 30 seconds: `10.min + 30.sec`.

---

## Wait for Key Press

In this case, the script will be paused until the player presses the specified key.

!!! info "Template"
```jsx
keybind { Keybind.<key> }
```
> - `<key>` - Keyboard key. You can find the [List of Keys](https://github.com/HollowHorizon/HollowEngine/blob/1.19.2/src/main/java/ru/hollowhorizon/hollowengine/common/util/Keybind.kt) in the mod's code.

---

## Wait for Right-Click on NPC

In this case, the script will wait until you right-click on an NPC.

!!! info "Template"
```kotlin
npc.waitInteract()
```

---

## Wait for Chat Messages

In this case, the script will continue after the specified message in the chat.

!!! info "Template"
Any text will work in this case.
```kts
var text by input()
```
Only the words "yes" and "no" will work in this case. The case of the characters does not matter, so you can write them in uppercase or lowercase.
```kts
var text by input("yes", "no")
```
