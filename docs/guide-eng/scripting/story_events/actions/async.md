# Asynchronous Actions

Sometimes you may need to run multiple actions simultaneously. In this case, there are two ways: <br>
1) Run multiple scripts at once. <br>
2) Use the `async { ... }` method. <br>

We'll discuss the second method here, and it works very simply.

---

## Basic Functionality

```kts
async {
    // Some task here
}
```

Inside `async`, you can write any actions: spawn NPCs, use loops and branches, in short, everything that you can do in regular scripts.
After starting the task, it will run in parallel with the main script.

---

## Additional Features

Sometimes you may need to stop or resume a paused asynchronous task from another part of the script, and this is also possible.
This is very useful in conjunction with infinite loops.

```kts
val task = async {
    // Some task here
}

task.stop() // Stop this task

task.resume() // Resume this task
```

You can only stop the task from the outside; I don't think there is a need to do this from within the task itself.