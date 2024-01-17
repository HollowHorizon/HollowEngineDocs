# Story Events

In HollowEngine, you can conveniently and quickly create various events with NPCs, cutscenes, dialogues, etc.

!!! danger "Important"
This type of script has many nuances and differs significantly from standard programming. It is not recommended for beginners unfamiliar with programming and those who do not understand how lambda expressions, delegate variables, and state machines work.

## How It Works?

First, you need to understand what a `Story Event` is, what it consists of, and who it is executed for.

### Basics

To begin with, remember that all story events are executed not for a single player but for a whole *team*. Whether you are creating a story for one player or not, it is not an excuse to write lower-quality code. You can obtain the team through the `team` variable.

The story event itself is a list of various commands. For example:

1) Create an NPC named Vitalik at coordinates `x, y, z` with the model `model.gltf`.
2) Give the NPC tasks to go to the coordinates `x1, y1, z1`. Wait until the NPC reaches the required point.
3) Write a message to the chat for all players in the team: "\[Stranger\] Help, I'm lost..."

Each of these commands is called a **node**, and the entire event represents a connected graph of these nodes. Some nodes may contain other nodes, for example, *loops*, where there is only one node but it contains other nodes that can repeat. Or *branches*, where there is also only one node, but it has 1 condition and 2 branches.

The event has many standard nodes, in which the entire logic is already written, and the data for each of these nodes is saved. But if you plan to go beyond just clicking on standard mechanics, you will need to understand how to create your nodes and how to save their data.

### Script Stages

A Story Event has 2 stages: <br>
1) Script loading <br>
> At this stage, all methods for creating nodes are called. In other words, everything you write in the script will be first loaded into the state machine, which will serve your events and take care of saving and handling errors. <br>
2) Script execution <br>
> At this stage, your script is already executed, and the nodes themselves are serviced by the game. That is, passing through the story itself takes place.

### Methods

Almost every method you write in the script will most likely not perform its action but rather load the corresponding *node* into the state machine or create new lists of nodes, such as loops, branches, or dialogs. For example, suppose the method `createCoolNpc()` will not create an NPC, surprisingly, but will load the `CoolNpcCreationNode` node into the state machine.

### Variables

Almost all variables will need to be obtained through delegates because delegates get the value only when accessing the variable, not when creating it. Also, delegated variables can be saved when the game stops or passed between different scripts. As you know, the script consists of nodes, so essentially, a variable represents two types of nodes:
1) Create a value of a certain type.
2) Write a value.
3) Get a value.

For example:
```kotlin
var reputation by saveable { 0 } //Create a value of a certain type

npc say { "Your reputation: $reputation" } //Get a value

// Use the `next` method with a lambda to perform this action during the script execution, not during its loading into the state machine. In the case of the method above, this action is already launched during the script execution, so `next` is not required.
next { reputation++ } //Write a value
```

## How to Launch Events?

To launch events, use the command `/hollowengine start-script <target> <file>`. Note that the target of the script is not the player you specify but **their team command**.



If you need the script to be launched together with the player's first entry, add the annotation: `@file:EntryPoint`, at the beginning of the script to tell the engine to run this script for each new player.