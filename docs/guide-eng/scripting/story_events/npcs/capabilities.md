# NPC Actions

There are quite a few different actions that NPCs can perform. The main ones are presented here.

# Character Speech

!!!note "Template"
```kts
npc say { "Hello!" }
```

---

## Item Actions

### Drop Item

The character can throw the specified item in the direction they are looking. It is done like this:

!!!note "Template"
```kts
npc dropItem { item("minecraft:apple") }
```
You can easily specify the item. Just take the item you need in your main hand and then use the command `/hollowengine hand`. The item data will be copied, including quantity and NBT tags.

### Hold Item

The character can hold an item in their right or left hand.

![NPC holds item in hand-2](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/npc-give-item2.gif)

!!!note "Template"
Give the item to the right hand:
```kts
npc giveRightHand { item("minecraft:apple") }
```
Give the item to the left hand:
```kts
npc giveLeftHand { item("minecraft:apple") }
```
You can easily specify the item. Just take the item you need in your main hand and then use the command `/hollowengine hand`. The item data will be copied, including quantity and NBT tags.

---

### Request Items

You can give a task to bring something to the NPC.

!!!note "Template"
```kts
npc requestItems {
text = "Quickly brought me these items:" // Message when right-clicking on the NPC. After that, a list of items will be displayed.
+item("minecraft:apple")
}
```
You can easily specify the item. Just take the item you need in your main hand and then use the command `/hollowengine hand`. The item data will be copied, including quantity and NBT tags.

## Interaction with the World

### Use Block

Characters, unlike iron golems, can use not only buttons but also any blocks on right-click :)

!!!note "Template"
```kts
npc useBlock { pos(x, y, z) } // Interact with the block located at coordinates x, y, z
```
> `pos(x, y, z)` - Block position to interact with. You can get the block you are looking at with the command /hollowengine pos

---

# Attack Target

To attack someone, the NPC needs to be given someone to target.

!!!note "Template"
Set the target, entity:
```kts
npc setTarget { entity }
```
Set the target, another character:
```kts
npc1 setTarget npc2
```
Set the target, command:
```kts
npc setTargetTeam { team }
```
Reset the target:
```kts
npc setTarget { null }
```

---
