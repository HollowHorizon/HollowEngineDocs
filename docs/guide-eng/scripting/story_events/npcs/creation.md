# NPC Creation and Spawning

## Creating a Character

To create an NPC, you can use the following template:

!!!note "Template"
```kts
// Here we create a delegate variable through which we will access our character. The NPC will be spawned as soon as this code is called.
val npc by NPCEntity.creating {
name = "Vitalik" // NPC name
model = "hollowengine:models/entity/player_model.gltf" // Path to the character model
attributes = Attributes( // List of character attributes (health, speed, etc.) - just like in the /attribute command
"minecraft:generic.max_health" to 100f // for example, health
)
size = 0.6f to 0.8f // NPC hitbox size (under development)
showName = true // show the nickname with the NPC name
transform = Transform( // Initial model parameters: translation, rotation, and scale
tX=1.5f // shift our model by 1.5 blocks on the x-axis.
)
animations[AnimationType.IDLE] = "<newAnimationName>" // Replace the default animation with a custom one (the engine automatically detects standard animations by default)
world = "minecraft:overworld" // dimension where to spawn the NPC
pos = pos(x, y, z) // coordinates where to spawn the NPC
}
```

The path to the model is specified in [ResourceLocation](../../../../features/resources) format.

When this fragment is executed, an NPC will be created at the specified coordinates, or the one that already exists in the world will be taken. (in this case, it will not be moved to these coordinates)

Next, using this variable, you can interact with the NPC in the world.

---

### Random Spawn

!!!info "Spawn the character near a random player"
If you need the character to spawn near a random player's command, you can use this method to find a random spawn point
```kts
pos = team.randomPos() //in brackets you can specify the radius, for example, 25f - for 25 blocks
```

---

### Attributes

!!!info "You can find all existing attributes using the command `/attribute <target>`"

    All you have to do is specify, where `attributes` is, this:
    
    ```kotlin
    Attributes("<attributeName>" to <float>)
    ```
    > Designations: 
    > - `attributeName` - the name of the attribute.
    > - `float` - Floating point number/digit, ending with `f`, example: `10f`

---

## Deleting a Character

To delete a character, simply call its `despawn()` method.

!!!note "Template"
```kts
npc.despawn()
```
---
