# Changing Player Models

To change the model of a player, you first need to obtain the desired player from the team command:

```kotlin
val player by team[{ "Player Nickname" }]
```

Now you can configure it.

```kotlin
player configure {
    model = "hollowengine:models/entity/player_model.gltf" // Replacing the player's model. Specified in the ResourceLocation format.
    animations[AnimationType.IDLE] = "animationName" // Replacing standard character animations. You can check the names of all animations with the command /hollowengine model <model>.
    textures["original_name"] = "hollowengine:textures/skins/my_skin.png" // Replacing the standard texture. You can check the names of the original textures with the command /hollowengine model <model>. The textures themselves are specified in the ResourceLocation format.
    transform = Transform( // Model parameters: translation, rotation, and scale
            tX=1.5f // Move our model 1.5 blocks to the right.
    )
}
```

The path to the model is specified in the [ResourceLocation](../../../../features/resources) format.

!!! note "Restore the player back."
    To revert to the default player model, simply use the string `%NO_MODEL%` instead of the model.