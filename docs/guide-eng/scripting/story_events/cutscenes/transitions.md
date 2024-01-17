# Screen Fade Effect

This section provides information on the setup and use of the screen fade effect. In addition to the fade itself, you can add text or an image for the transition.

### Example of Setting Up the Effect and Customization:

```kotlin
// Start the transition
fadeIn {
    text = "Big text"
    subtitle = "Text smaller, below the big one"
    texture = "modid:textures/your_texture.png"
    color = 0xFFFFFF // Texture color
    time = 10.sec // Transition time
}

// Now you can perform some actions "behind the scenes," such as teleporting the player or whatever you need...
    
// To show the screen again, do not end the transition
fadeOut {
    text = "Big text"
    subtitle = "Text smaller, below the big one"
    texture = "modid:textures/your_texture.png"
    color = 0xFFFFFF // Texture color
    time = 10.sec // Transition time
}
```
    
    - Tips: 
    > - The `time` parameter is specified as an integer:
    >  - `20` - 20 ticks. (1 second) 
    >  - `3.sec` - Time in seconds. 
    >  - `5.min` - Time in minutes. 
    >  - `10.hour` - Time in hours. 
    >  - You can also combine them using `+`, For example: `1.hour + 15.min + 30.sec + 45`. 
    >  - The `color` parameter is specified as a [hex color](https://htmlcolors.com/google-color-picker).
    >  - You need to write `0x` at the beginning and then only 6 digits. 

---