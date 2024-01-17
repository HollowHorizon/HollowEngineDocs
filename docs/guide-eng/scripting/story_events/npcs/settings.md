# NPC Configuration

In addition to the basic configuration during spawn, you can also change various parameters of an NPC during the script, such as the model, texture, default animations, position, rotation, and sizes.

!!! note "Template"
```kts
npc configure {
model = "hollowengine:models/entity/player_model.gltf" // Replace the NPC model. Specified in the ResourceLocation format.
animations[AnimationType.IDLE] = "animationName" // Replace the default NPC animations. You can view the names of all animations with the command /hollowengine model <model>.
textures["original_name"] = "hollowengine:textures/skins/my_skin.png" // Replace the default texture. You can view the names of the original textures with the command /hollowengine model <model>. The textures themselves are specified in the ResourceLocation format.
transform = Transform( // NPC model parameters: translation, rotation, and scale
tX=1.5f // Move our model 1.5 blocks along the x-axis.
)
}
```
The path to the model is specified in the [ResourceLocation](../../../../features/resources) format.
