# Event List

HollowEngine adds a standard event list, which opens by pressing the `~` / `Ё` key. You can change the key in the control menu.

## Adding an Event to the List

!!!note "Template"
```kts
ProgressManager.addMessage { "Get 10 cobblestones" }
```

## Removing an Event from the List

!!!note "Template"
```kts
ProgressManager.removeMessage { "Get 10 cobblestones" }
```
In this case, you need to write exactly the same message to remove it.
