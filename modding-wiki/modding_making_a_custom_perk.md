---
title: Modding: Making a Custom Perk
source: https://noita.wiki.gg/wiki/Modding:_Making_a_custom_perk
category: modding-wiki
---

# Modding: Making a Custom Perk

This documentation guides you through the process of creating and integrating custom perks into Noita. Understanding how to define and register new perks is essential for expanding the game's mechanics and offering unique gameplay experiences through mods.

## Create & Register Your Perk

To add a custom perk to Noita, you need to define its properties and register it with the game's perk system.

1.  **Define Your Perk:**
    Add a new Lua file to your mod's `files` directory (e.g., `files/perk_list.lua`). Within this file, append your custom perk definitions to the global `perk_list` table. Repeat the following structure for each perk you wish to add:

    ```lua
    table.insert(perk_list,
         {
           id = "MY_CUSTOM_PERK",
           ui_name = "My Custom Perk Name",
           ui_description = "A Fancy Description",
           ui_icon = "data/ui_gfx/perk_icons/electricity.png",  -- Replace with your custom icon path
           perk_icon = "data/items_gfx/perks/electricity.png",  -- Replace with your custom perk icon path
           game_effect = "PROTECTION_ELECTRICITY",  -- Hardcoded game effect, change or remove if not needed
           usable_by_enemies = false,
           not_in_default_perk_pool = false, -- Set to true to exclude from the default perk pool
           func = function( entity_perk_item, entity_who_picked, item_name )
             -- Code to execute when the perk is picked up goes here.
           end,
         }
    )
    -- If you have more perks to add, repeat the structure:
    table.insert(perk_list,
         {
           id = "MY_CUSTOM_PERK_TWO",
           -- ... other properties
         }
    )
    ```

2.  **Register Your Perk File:**
    In the very beginning of your mod's `init.lua` file, add the following line to ensure your custom perk definitions are loaded:

    ```lua
    ModLuaFileAppend("data/scripts/perks/perk_list.lua", "mods/<MY_AWESOME_MOD>/files/perk_list.lua")
    ```
    Replace `<MY_AWESOME_MOD>` with the actual name of your mod.

3.  **Completion:**
    After these steps, your custom perk should be integrated into the game.

**Note:**
`game_effect`s are typically hardcoded in-engine effects. While you can string them together or omit them to implement custom effects via Lua, they are not directly customizable through Lua scripting.

For a list of available `GAME_EFFECTS`, refer to [Modding: Enums](https://noita.wiki.gg/wiki/Modding:_Enums#GAME_EFFECTS) or examine the `data/scripts/perks/perk_list.lua` file in the game's data.

## Spawning and Picking Up a Perk

If you wish to spawn and pick up a perk programmatically via script, rather than relying on natural in-game spawns (like in Holy Mountains), you can use the following code snippet:

```lua
-- IMPORTANT: If placing this in init.lua, ensure it runs *after* the ModLuaFileAppend line
-- and after the player has spawned. The OnPlayerSpawned callback is a suitable place.
dofile_once("data/scripts/perks/perk.lua")

function OnPlayerSpawned(player_entity)
    -- Spawn the perk entity in the world at the player's current location
    local x, y = EntityGetTransform(player_entity)
    local perk = perk_spawn(x, y, "MY_CUSTOM_PERK")

    -- To pick up the perk instantly, you can add the following lines:
    perk_pickup(perk, player_entity, EntityGetName(perk), false, false)
end
```

## Checking for Active Perks

When a perk is picked up using the default `perk_pickup()` function, it is registered as a "run flag" with the format `PERK_PICKED_<PERK_ID>`. You can use the following Lua function to easily check if a specific perk is currently active:

```lua
function has_perk(perk_id)
  return GameHasFlagRun("PERK_PICKED_" .. perk_id)
end
```

## Translations

Noita supports multiple languages, and any in-game text, including perk names and descriptions, must be compatible with its translation system. This requires appending specific lines with a defined number of columns (separators) to the `data/translations/common.csv` file.

For detailed instructions on how to add custom names to translations, refer to:
*   [Modding: Utilities#Add custom names in translations](https://noita.wiki.gg/wiki/Modding:_Utilities#Add_custom_names_in_translations)

## Further Reading

*   The base game's perk definitions can be found in `data/scripts/perks/perk_list.lua`.
*   The core implementation of perks, including functions like `perk_spawn()` and `perk_pickup()`, is located in `data/scripts/perks/perk.lua`.