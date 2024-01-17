# Basic Features

**Before you start:**
If you want to add a character to the dialogue, you need to create it before the dialogue, not directly in it.

## Starting a Dialogue

To enter the dialogue space, simply type `dialogue` and open curly braces. Further actions will be written in this space.

### Template
```kotlin
dialogue {
    // Your actions will go here...
}
```

## Actions

Currently, the dialogue window has several unique features. However, you can also use actions from the main script space (for example, [character animations](../../npcs/animations))

### Character Dialogue

!!! note "Text from the Npc"
    ```kts
    npc say { "Hi!" }
    ```
    As this action is in the dialogue space, its effect will override the chat, and the message will appear in the dialogue window.

---

!!! note "Text from the team leader."
    ```kts
    team send { "Hi!" }
    ```
    As this action is in the dialogue space, its effect will override the chat, and the message will appear in the dialogue window.



---

!!! info "Just a text, for example: Author's words."
    ```kts
    send { // Manually specify: name - Name in the dialogue window, text - the text to be displayed.
        name = "Unknown"
        text = "Hello, have we met before?"
        }
    ```

### Choice Options

Choices are created only within the dialogue space; otherwise, it will simply state that the `choice` was not found.

!!! info "Template"
    ```kotlin
    choice {
        "Your choice 1" {
            //Actions when chosen
        }
        "Your choice 2" {
            //Actions when chosen
        }
        // And so on...
    }
    ```

The dialogue will end when there are no more phrases and other choices.



