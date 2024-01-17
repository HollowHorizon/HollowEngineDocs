# Resource Loader

HollowEngine provides its own resource loader. First of all, **each mod has its own set of resources**, and each of these sets is divided into **client** and **server** resources.
By using this resource loader, you can add your resources to HollowEngine and other mods.

## Client Resources

Client resources are resources that are applied only on clients. These primarily include: models, textures, sounds, translations, etc. <br>
In simpler terms, these are basic resource packs that will be added in any case.

To add your resources, you need to place them at the path: `.minecraft/hollowengine/assets/<modid>/<path>/`, where: <br>
・ `<modid>` - the mod id to which you want to add the resource, for example: `hollowengine`. <br>
・ `<path>` - the path to the file you want to add, for example: `models/entities/`. <br>

For example, you can store your character models at this path: `.minecraft/hollowengine/assets/hollowengine/models/entities/`.

After changing the resources, press F3+T to reload the client resources.

## Server Resources

Server resources are resources that are stored only on the server, such as recipes, loot tables, structures, etc.
In simpler terms, these are data packs that will be loaded when entering the world.

To add your resources, you need to place them at the path: `.minecraft/hollowengine/data/<modid>/<path>/`, where: <br>
・ `<modid>` - the mod id to which you want to add the resource, for example: `hollowengine`. <br>
・ `<path>` - the path to the file you want to add, for example: `recipes`. <br>

For example, you can store your data pack recipes at this path: `.minecraft/hollowengine/data/hollowengine/recipes/`.

After changing the data, you need to run `/reload` to reload the server resources.

## Resource Location

Resource Location is the way to record the path to a mod file within the code.

Suppose you placed the file `my_cool_model.gltf` at the path `.minecraft/hollowengine/assets/my_super_mod/models/entities/`, then the Resource Location should be written as: `"my_super_mod:models/entities/my_cool_model.gltf"`, where the colon separates the mod and the relative path.
