---
title: Modding Basics
source: https://noita.wiki.gg/wiki/Modding:_Basics
category: modding-wiki
---

# Modding: Basics

This documentation covers the fundamental concepts of Noita modding, including the directory structure, the Entity Component System, and how to use Lua scripts to modify game behavior. Understanding these basics is crucial for creating and implementing custom content for Noita.

## Mod Installation Locations

There are two primary locations for installing mods:

*   `Noita/mods/`: Use this directory for manually downloaded mods or for active mod development.
*   `steamapps/workshop/content/881100/`: This is where mods downloaded through the Steam Workshop are stored.

## Mod Directory Structure

A typical mod follows a specific directory structure to organize its files.

```
myAwesomeMod/
├── data/
│   └── enemies_gfx/
│       └── player.png
├── files/
│   └── my_custom_script.lua
├── init.lua
└── mod.xml
```

Here's a breakdown of the key directories and files:

*   `myAwesomeMod/`: This is the root folder for your mod. The name you choose here will be used in file paths within your mod's code. This is **not** the visible name of the mod in the game's menu.
*   `data/`: This folder mirrors the structure of Noita's extracted [data files](https://noita.wiki.gg/wiki/Data.wak). Use this directory **only** for adding new enemies or replacing sprites. It's generally recommended to avoid directly replacing base game files to ensure compatibility with other mods. For editing Lua or XML files, prefer using the provided APIs to append or modify existing content.
    *   `enemies_gfx/`: A subfolder within `data/` that typically holds enemy and friendly spritesheets.
    *   `player.png`: An example of a player animation spritesheet. When placed within the `data/` folder of a mod, it directly replaces the base game spritesheet.
*   `files/`: This directory is intended for all custom assets, scripts, and data that you don't want to directly overwrite existing game files. This is the preferred location for most custom content.
    *   `my_custom_script.lua`: An example of a custom Lua script file. You can place any custom scripts here and call them from other parts of your mod.
*   `init.lua`: This is the entry point for your mod. It allows you to hook into various game events, such as world initialization and player spawning, and is where you can manage file overrides.
*   `mod.xml`: This file contains the [mod metadata](https://noita.wiki.gg/wiki/Modding:_Mod.xml), including the mod's name, description, and other configuration settings.

### Referencing Files in Different Paths

The `data/` and `files/` directories are handled differently by the game. Files within the `data/` directory are treated as part of a virtual filesystem and can be referenced directly. Files in other directories, like `files/`, require their full mod path to be specified.

**Lua Example:**

```lua
-- Partial path for data files (even if overwritten or not in your mod)
dofile_once("data/scripts/lib/utilities.lua")

-- Full path for your own scripts
dofile_once("mods/myAwesomeMod/files/scripts/my_custom_script.lua")
```

This same principle applies when defining paths in XML files for assets like spritesheets, projectiles, or effects.

## The Entity Component System Basics

Noita utilizes an Entity Component System (ECS) for managing game objects. Entities are the fundamental building blocks and follow these rules:

*   Entities can contain any number of components, including duplicates of the same component.
*   Entities can have child entities, which can define their own components.
*   Entities can inherit functionality from other entities.
*   Each entity can have only one unique name.
*   Entities can be associated with multiple tags.

### Example

Let's examine a simple entity from the base game file `data/entities/props/banner.xml`:

```xml
<Entity tags="prop">

  <VelocityComponent />

  <SimplePhysicsComponent />

  <SpriteComponent
    z_index="1"
    image_file="data/props_gfx/banner.xml"
    offset_x="0"
    offset_y="0"
  ></SpriteComponent>
</Entity>
```

This entity is composed of three components:

*   `VelocityComponent`: Essential for entities that interact with physics. It can define various properties, including gravity. In this example, it's initialized with default values.
*   `SimplePhysicsComponent`: Provides basic physical properties, causing the entity to fall and stop at obstacles. It does not support complex collisions or interactions like being kicked. For more advanced physics, `PhysicsBodyComponent` and `PhysicsShapeComponent` are used.
*   `SpriteComponent`: Attaches an image file to the entity. If the `image_file` points to an XML file, it indicates an animated sprite. For static images, a direct file path can be used.

The `image_file` attribute in `SpriteComponent` references `data/props_gfx/banner.xml`, which defines the sprite's metadata:

```xml
<Sprite
  filename="data/props_gfx/banner.png"
  offset_x="12"
  offset_y="30"
  default_animation="stand">

  <!-- stand -->
  <RectAnimation
    name="stand"
    pos_x="0"
    pos_y="0"
    frame_count="7"
    frame_width="32"
    frame_height="32"
    frame_wait="0.11"
    frames_per_row="7"
    loop="1"
  ></RectAnimation>
</Sprite>
```

This XML defines the actual image file (`banner.png`) and its animation details. The `<RectAnimation>` element specifies the frames, dimensions, and timing for the "stand" animation.

## Creating and Deleting Entities

Entities can be created and destroyed using Lua functions:

*   **Spawn Entity:** `EntityLoad("path/to/entity.xml", x, y)`
*   **Delete Entity:** `EntityKill(entity_id)`

Other components and systems also offer ways to manage entities:

*   `ProjectileComponent::spawn_entity`: Spawns an entity upon projectile collision.
*   `CameraBoundComponent`: Limits the spawn rate or distance of frequently used entities relative to the camera.
*   `LifetimeComponent`: Assigns a specific duration for an entity's existence.
*   `DamageModelComponenet`: Enables hitpoints and damage taking. The entity is killed when its health reaches zero.

## Tags

Both entities and components can be assigned any number of tags. Tags are a simple method for categorizing "things" and can be created dynamically. For instance, to find all enemies near the player, you can use `EntityGetWithTag("enemy")`.

While most tags are purely for categorization, a set of [special tags](https://noita.wiki.gg/wiki/Modding:_Special_tags) have hard-coded functionality within the engine.

**Important Notes on Tags:**

*   Entity tags are defined in the `tags` attribute, while component tags use the `_tags` attribute.
*   The engine has a limited capacity for custom global tags to ensure inter-mod compatibility. Community testing suggests limits around 224 for entity tags and 210 for component tags.
*   [Special tags](https://noita.wiki.gg/wiki/Modding:_Special_tags) are fundamental to the ECS and should be thoroughly understood.

## Entity Inheritance

Entity inheritance is implemented using the `Base` component.

*   The `file` attribute within the `Base` component specifies the path to the base entity file.
*   To override components from the base entity, define new components with the same name **inside** the `Base` element. The base entity **must** already possess the component you intend to override; otherwise, an error will occur.
*   Additions to the entity are placed normally outside the `Base` element.
*   An entity can inherit from multiple base entities.
*   All tags from inherited entities are combined.

## init.lua

The `init.lua` file is the first script executed for any mod. It provides predefined function names that can be used to hook into specific game events and serves as a central place for managing file overrides. The following code snippets are illustrative examples.

### Available Function Hooks

```lua
-- Called in order upon loading a new game:
function OnModPreInit() end
function OnModInit() end
function OnModPostInit() end

-- Called when the player entity has been created. Ensures chunks around the player have been loaded & created.
function OnPlayerSpawned(player_entity) end

-- Called when the player dies
function OnPlayerDied( player_entity ) end

-- Called once the game world is initialized. Doesn't ensure any chunks around the player.
function OnWorldInitialized() end

-- Called *every* time the game is about to start updating the world
function OnWorldPreUpdate() end

-- Called *every* time the game has finished updating the world
function OnWorldPostUpdate() end

-- Called when the biome config is loaded.
function OnBiomeConfigLoaded() end

-- The last point where the Mod API is available. After this materials.xml will be loaded.
function OnMagicNumbersAndWorldSeedInitialized() end

-- Called when the game is paused or unpaused.
function OnPausedChanged( is_paused, is_inventory_pause ) end

-- Will be called when the game is unpaused, if player changed any mod settings while the game was paused
function OnModSettingsChanged() end

-- Will be called when the game is paused, either by the pause menu or some inventory menus. Please be careful with this, as not everything will behave well when called while the game is paused.
function OnPausePreUpdate() end
```

### Overriding and Extending Systems

These lines are typically placed at the end or beginning of `init.lua` and execute after all mod filesystems have been registered.

```lua
-- Appends the content of 'actions.lua' to 'gun_actions.lua'
ModLuaFileAppend("data/scripts/gun/gun_actions.lua", "mods/mymod/files/actions.lua")

-- Appends the content of 'potion_appends.lua' to 'potion.lua'
ModLuaFileAppend("data/scripts/items/potion.lua", "mods/mymod/files/potion_appends.lua" )

-- Overrides specific magic numbers using the provided XML file
ModMagicNumbersFileAdd("mods/mymod/files/magic_numbers.xml")

-- Appends custom materials to the game's material list
ModMaterialsFileAdd("mods/mymod/files/custom_materials.xml")

-- Registers custom FMOD sound events. Event mapping files can be generated in FMOD Studio.
ModRegisterAudioEventMappings("mods/mymod/files/audio_events.txt")
```

## Important and Interesting Files

### Files Recommended for Review

*   `magic_numbers.xml`: Contains numerous variables that control various aspects of gameplay, from virtual resolution to animal blood amounts. Reviewing this file is highly recommended.

### Files Less Critical for Beginners

*   `genome_relations.csv`: A table detailing the relationships between all in-game animals (including the player). This file can be freely edited to alter AI behavior, such as making all creatures friendly towards the player.
*   `translations/common.csv`: Contains all basic game translations. This is useful for cross-referencing spell names, as much of the in-game text is defined here. It can also be edited to rename or rewrite game elements.
*   `scripts/wang_scripts.csv`: Registers "global" biome functions that are accessible by all wang tiles and pixel scenes. Note that each biome still requires its own implementation for these functions. This file can be edited to add custom functions.
*   `post_final.frag`: The main OpenGL shader file. It can be edited and appended to create custom shader effects, but this is not recommended without prior experience in programming and shaders.

### Lists of Interest

*   **Materials:** `data/materials.xml`
*   **Perks:** `data/scripts/perks/perk_list.lua`
*   **Potions:** `data/scripts/items/potion.lua`
*   **Spells:** `data/scripts/gun/gun_actions.lua`
*   **Status Effects:** `data/scripts/status_effects/status_list.lua`

Refer to the `init.lua` section for information on how to extend these lists.

## Debugging

Noita does not currently offer a dedicated IDE or testing environment. Mod development often involves frequent game restarts to test changes. Here are common debugging methods:

1.  **Development Build (`noita_dev.exe`):**
    *   This executable starts with a development console, which is invaluable for identifying Lua and XML errors as they occur.
    *   It's typically located in `tools_modding/` but must be launched from the root Noita directory (alongside `noita.exe`).
    *   Press `F1` for a list of keybinds and `F5` to enable most debugging features.
    *   `print()` statements will output to this console. `GamePrint()` displays messages in the lower-left corner of the in-game screen.
    *   Note: This build can reduce performance for some users, so switching between the development and standard builds is acceptable.

2.  **Logging to File:**
    *   This can be enabled via specific magic numbers in `magic_numbers.xml`.
    *   Alternatively, a mod like [Modworkshop](https://modworkshop.net/mod/25910) can provide this functionality.
    *   Logs are written to `Noita/logger.txt`.

3.  **CheatGUI Mod:**
    *   Excellent for testing gameplay features without delving into debug menus.
    *   Allows spawning items, perks, and wands, teleporting, increasing health, and more directly from the in-game HUD.
    *   Download: [Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=1984977713) \| [Github](https://github.com/probable-basilisk/cheatgui)

4.  **Decoda Lua Debugger:**
    *   Noita supports the [Decoda Lua debugger](https://unknownworlds.com/decoda/).
    *   Requires separate setup. Instructions can be found in `tools_modding/lua_debugging.txt`.

**Important Note:** While the game is intended to detect mod file changes and restart automatically when a new game begins, this feature is not always reliable. It is advisable to manually exit and restart the game entirely after making modifications.