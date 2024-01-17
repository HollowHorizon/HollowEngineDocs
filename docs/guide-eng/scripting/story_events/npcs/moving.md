# NPC Movement

First of all, a character can move towards various targets:

![NPC moving to a point](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/npc-move.gif)

## Block

You can specify a block as the target.

If you want the character to come to the block, and the code to continue, use:
```kotlin
npc moveToPos { pos(x, y, z) }
```

There is also an option to simply set a target, and the character will always strive there until told to stop:
```kotlin 
npc setMovingPos { pos(x, y, z) }
```

And, of course, to stop, simply specify an empty target:
```kotlin 
npc setMovingPos { null }
```

## Entity / Mob

You can specify a mob, player, or another character as the target.

If you want the character to come to another character, you shouldn't use curly braces:
```kotlin
npc1 moveToEntity npc2
```
And for a mob, it would be:
```kotlin
npc1 moveToEntity { entity }
```

Similarly, you can specify a permanent target or `null`:
```kotlin 
npc1 setMovingEntity npc2 //character

npc setMovingEntity { entity } //mob

npc setMovingEntity { null } //nothing
```

## Player Team

In this method, the nearest player of the team will be selected, and the character will follow them.

For a one-time action, you should write:
```kotlin
npc1 moveToTeam { team }
```

And for permanent following:
```kotlin
npc setMovingTeam { team } //follow

npc setMovingTeam { null } //stop following
```

# NPC View Direction

You can tell the character to look at a particular object. Similarly to the previous cases, there are commands for permanent focus or a one-time task.

![NPC looking at a point](https://raw.githubusercontent.com/HollowHorizon/HollowEngineDocs/main/docs/hollowengine-guide/.resourses/npc-look.gif)

## Block

One-time task:
```kotlin
npc lookAtPos { pos(x, y, z) }
```

Permanent task:
```kotlin
npc setLookingPos { pos(x, y, z) } //start looking 

npc setLookingPos { null } //stop looking 
```

## Entity / Mob

One-time task:
```kotlin
npc1 lookAtEntity npc2 //for characters

npc lookAtEntity { entity } //for other entities
```

Permanent task:
```kotlin
npc1 setLookingEntity npc2 //start looking at an npc 

npc setLookingEntity { entity } //start looking at an entity

npc setLookingEntity { null } //stop looking 
```

## Player Team

One-time task:
```kotlin
npc lookAtTeam { team }
```

Permanent task:
```kotlin
npc setLookingTeam { team } //start looking 

npc setLookingTeam { null } //stop looking 
```