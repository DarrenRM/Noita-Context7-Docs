---
title: Modding: Lua Scripting
source: https://noita.wiki.gg/wiki/Modding:_Lua_Scripting
category: modding-wiki
---

# Modding: Lua Scripting

This documentation provides essential information and examples for writing Lua scripts to modify Noita. Understanding how to hook into the game's systems and utilize Lua effectively is crucial for creating custom content and behaviors.

## Places to Hook Your Scripts

Noita's modding system allows you to inject your Lua code at various points. Choosing the right place depends on what you want to achieve.

### `init.lua`

*   The recommended starting point for new mods.
*   This file is unique to your mod and doesn't require overwriting existing game files.
*   Refer to [Modding Basics](https://noita.wiki.gg/wiki/Modding:_Basics#init.lua) for more details.

### `data/scripts/gun/gun.lua`

*   This script is executed every time a wand is fired.
*   It's deeply integrated with the game's core engine code.
*   Be mindful of compatibility issues when modifying this file, as explained below.

### `data/scripts/biomes/<biome_name>.lua`

*   These scripts are called once when the player enters a specific biome.
*   Compatibility considerations are important here as well.

### `<LuaComponent>`

*   This is a highly versatile and commonly used method for integrating custom code.
*   Many game elements and behaviors defined in `data/scripts/` are actually implemented using this component.
*   Consult the official `lua_api_documentation.txt` for a comprehensive list of actions you can hook into using this component.

### Hooking in a Compatible Way

When modifying scripts that are heavily used by the game or other mods, it's often better to *append* your code rather than overwriting the original file. This approach ensures better compatibility by allowing your code to be executed in the order your mod is loaded, preventing forceful overwrites.

This can only be done within `init.lua`.

```lua
-- The gun.lua is just an example; any file can be appended to.
ModLuaFileAppend("data/scripts/gun/gun.lua", "mods/mymod/files/gun.lua")
```

## Lua Notes and Tips

### Restricted Libraries

Certain standard Lua libraries and functions are restricted within Noita's modding environment to maintain game stability and security. An incomplete list includes:

*   `IO`
*   `OS`
*   `require`

The Noita Lua API provides reimplementations for much of the functionality found in these restricted libraries.

```lua
-- This is not allowed:
-- local file = require "/mods/MODNAME/files/somefile.lua"
-- Instead, use:
local file = dofile_once("/mods/MODNAME/files/somefile.lua")

-- This is not allowed:
-- local time = os.time()
-- Instead, use:
local year,month,day,hour,minute,second = GameGetDateAndTimeLocal()
local time = year .. month .. day .. hour .. minute .. second
```

Without direct access to the `IO` library, saving persistent data between game sessions is more challenging. The primary methods for storing persistent data are using flags or the `mod_settings` file.

For more detailed information, refer to the [Restricted API](https://noita.wiki.gg/wiki/Modding:_Lua_API#Restricted_API) section of the Lua API documentation.

## Script Examples

Here are practical examples of common Lua scripting tasks in Noita modding.

### Get the Current Entity

This retrieves the entity within which your script is currently executing, typically when using a `<LuaComponent>`. Note that not all scripts run this way (e.g., `init.lua`).

```lua
local entity = GetUpdatedEntityID()
```

In the example above, `entity` could refer to the player, a wand, a projectile, or any other entity, depending on where the script is being run. This is the most straightforward way to get the current entity.

**Bonus:** In `data/scripts/gun/gun.lua`, this function will return the player entity.

### Get Player Entity

The utility script `utilities.lua` returns a list of player entities. You'll need to extract the first one for most common use cases. This function can serve as a backup if a specific hook doesn't directly expose the player entity.

```lua
dofile_once("data/scripts/lib/utilities.lua")

function get_player()
  local players = get_players()
  if players then
    return players[1]
  end

  -- Player is dead
  return nil
end

local player = get_player()
```

### Get Currently Held Wand

This function attempts to find the wand currently held by an entity, which can be useful for more than just the player.

```lua
dofile_once("data/scripts/gun/procedural/gun_action_utils.lua")

-- This function likely works on any entity with an Inventory2Component, such as some enemies.
local wand = find_the_wand_held(player)
```

### Get Currently Held Item (Including Wands)

This function retrieves the item currently active in an entity's inventory.

```lua
function get_held_item(animal)
  local inv_comp = EntityGetFirstComponentIncludingDisabled(
    animal, "Inventory2Component"
  )

  -- Although the component should always be present, unexpected issues might occur
  -- (e.g., interference from another mod).
  if not inv_comp then
    return nil
  end

  return ComponentGetValue2(inv_comp, "mActiveItem")
end

-- This should return a numeric ID representing the item.
local wand = get_held_item(player)
```

### Easily Add Items to Inventory

This utility function simplifies the process of adding items to an entity's inventory.

```lua
-- Note: The player is not the only entity that can have an inventory.
function add_items_to_inventory(player, items)
  for _, path in ipairs(items) do
    local item = EntityLoad(path)
    if item then
      GamePickUpInventoryItem(player, item)
    else
      GamePrint("Error: Couldn't load the item ["..path.."]!")
    end
  end
end

function OnPlayerSpawned(player)
  local items = {
    "data/entities/items/pickup/thunderstone.xml",
  }
  add_items_to_inventory(player, items)
end
```

### Spawn and Enable Perk

The perk system can be a bit complex. This example uses an existing function to spawn and then pick up a perk.

```lua
-- The perk system is somewhat intricate, so it's best to use existing functions.
dofile_once("data/scripts/perks/perk.lua")

local perk = perk_spawn(x, y, "PROTECTION_RADIOACTIVITY")

-- Omit this part if you only intend to spawn the perk in the world.
if perk then
  perk_pickup(perk, player, EntityGetName(perk), false, false)
end
```

### Spawn Most Other Things

This demonstrates how to spawn various entities, such as enemies or gold, into the game world.

```lua
-- Enemy
EntityLoad("data/entities/animals/duck.xml", x, y)

-- Gold
EntityLoad("data/entities/items/pickup/goldnugget_200.xml", x, y)
```

### Run Init Code Only Once

This pattern ensures that specific initialization code runs only when a new game starts, not when a savegame is loaded.

```lua
local LOAD_KEY = "MYMOD_FIRST_LOAD_DONE"

function OnPlayerSpawned(player)
  if GlobalsGetValue(LOAD_KEY, "0") == "1" then
    return
  end
  GlobalsSetValue(LOAD_KEY, "1")

  -- Place your initialization code here.
end
```

### Shoot a Projectile Through Lua

This function provides a convenient way to fire projectiles using Lua, handling some of the necessary setup for you.

```lua
dofile_once("data/scripts/lib/utilities.lua")

-- Define your starting position and velocities according to your desired rules.
shoot_projectile(player, "mods/mymod/files/projectiles/supernuke.xml", from_x, from_y, vel_x, vel_y)
```

While there is a direct API function `GameShootProjectile()`, the `shoot_projectile` utility function simplifies its usage by managing some of the prerequisite steps.