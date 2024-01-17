# HollowEngine Scripting Engine

HollowEngine allows you to write scripts in a slightly modified version of [Kotlin](https://kotlinlang.org/), tailored for in-game usage without the need for restarts. The language differs a bit from standard [Kotlin](https://kotlinlang.org/); for example, you don't have to create any methods. You can start writing code directly without worrying about creating methods and classes. However, you are free to create separate or nested classes and methods in your script files and use them in your code!

## How to Create a Script?

First of all, before writing scripts, you need to decide what kind of script you need. Currently, there are three types of scripts:


| Name | Type | Note |
| --- |--- | --- |
| Mod | mod | Runs like regular mods during the game loading. |
| [Story Event](story_events.md) | se | Runs on command in the world, or it can be triggered from a mod script. |
| Recipe | content | Runs when reloading recipes (and the /reload command accordingly) |

Once you've decided on the script type, create a text file in the `.minecraft/hollowengine/scripts/` folder. <br>
You can also create subfolders in this folder, for example, one for events and one for crafts, or divide all events into chapters to make it easier to work with.

Files should be named according to the pattern: `<name>.<type>.kts`, where: <br>
・ `<name>`: The name of the script. It is recommended to name scripts in lowercase without spaces. (you can use the underscore `_` instead of spaces) <br>
・ `<type>`: Your script type from the table. <br>

## What and How to Write in Scripts?

Each script has its own set of standard methods and variables. More details are explained in the section for each script type.

!!! note "Note"
To avoid conflicts with script names, it is recommended to place them in different folders. At the beginning of each script, add a `package` statement with the path to this folder relative to the `scripts` folder (using dots, not `/`), for example: `package ru.hollowhorizon.my_super_modpack`.

## Compiling Scripts

!!! danger "What to do if the script takes a long time or doesn't run?"
After running the script by command or during the game launch, the script will be compiled. This can take from 5 seconds to 3-5 minutes, depending on the script's size, the number of libraries and imports, and the PC's performance. If even after 3-5 minutes nothing happens and there are no errors in the chat, it is likely that you installed the lite version of HollowCore. Check the [installation](../../install) of mods.
After the first run, scripts are packed into a `jar` archive, allowing them to be launched almost instantly later. Of course, when you change the source script, the compilation will be performed again.

## IDE, Syntax Highlighting, Code Autocompletion.

While writing scripts, you can use any IDE like VSCode, but implementing **code autocompletion** is quite complex.
The easiest way is to fork the HollowEngine repository on GitHub. To do this: <br>
1. Clone the HollowEngine repository to your PC. <br>
2. Build the project: <br>
   ・ Wait for the project to be configured and indexed. <br>
   ・ Go to the gradle menu (on the right panel) and run: `HollowEngine -> Tasks -> forgegradle runs -> genIntellijRuns`. <br>
   ・ Compile the jar: `Tasks -> build -> jar`  <br>
3. Run the game through the task on the top right panel. <br>

After that, you can create scripts in the path: `run/hollowengine/scripts`. The indexing will be run again after creating the script.