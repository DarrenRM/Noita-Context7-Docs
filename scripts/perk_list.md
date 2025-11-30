---
title: perk_list
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/perks/perk_list.lua
---

# perk_list

This file, `perk_list.lua`, is a core data file for the game Noita. It defines the properties and behaviors of all the perks available to the player. Perks are special abilities or modifiers that significantly alter gameplay, offering advantages, changing character interactions, or introducing unique mechanics. This file acts as a central registry, mapping each perk's unique identifier to its visual representation, in-game effects, and how it interacts with the game's systems.

## File Structure

The `perk_list.lua` file is structured as a Lua table named `perk_list`. Each entry within this table represents a single perk and is itself a Lua table containing key-value pairs that describe the perk.

The general structure for a perk entry is as follows:

```lua
{
    id = "UNIQUE_PERK_ID",
    ui_name = "$perk_ui_name_key",
    ui_description = "$perkdesc_ui_description_key",
    ui_icon = "path/to/ui/icon.png",
    perk_icon = "path/to/perk/icon.png",
    game_effect = "OPTIONAL_GAME_EFFECT_TAG", -- Not always present
    stackable = STACKABLE_YES or STACKABLE_NO,
    stackable_is_rare = true, -- Optional, for rare stackable perks
    usable_by_enemies = true, -- Optional, if enemies can also have this perk
    max_in_perk_pool = number, -- Optional, limits how many times this perk can appear in a pool
    func = function(...) ... end, -- Optional, function executed when the perk is acquired
    func_remove = function(...) ... end, -- Optional, function executed when the perk is removed
}
```

**Key Components:**

*   **`id`**: A unique string identifier for the perk. This is crucial for referencing the perk within the game's code.
*   **`ui_name`**: A string that references a localization key (prefixed with `$`) for the perk's display name in the user interface.
*   **`ui_description`**: A string that references a localization key (prefixed with `$`) for the perk's description in the user interface.
*   **`ui_icon`**: The file path to the icon displayed in the perk selection menu.
*   **`perk_icon`**: The file path to the icon displayed in the player's inventory or status.
*   **`game_effect`**: An optional string tag that might be used by the game engine to categorize or apply general effects.
*   **`stackable`**: A boolean value (`STACKABLE_YES` or `STACKABLE_NO`) indicating whether the perk can be acquired multiple times.
*   **`stackable_is_rare`**: An optional boolean that marks stackable perks as rarer.
*   **`usable_by_enemies`**: An optional boolean indicating if enemies can also possess this perk.
*   **`max_in_perk_pool`**: An optional numerical value that limits the number of times a perk can appear in a specific perk selection pool.
*   **`func`**: An optional Lua function that is executed when the player acquires the perk. This function often modifies game state, adds components to the player entity, or triggers other game events.
*   **`func_remove`**: An optional Lua function that is executed when the perk is removed from the player. This function typically reverses the effects of the `func` function.

The file also defines global constants `STACKABLE_YES` and `STACKABLE_NO` for clarity.

## Key Patterns

Several patterns and organizational principles are evident in the `perk_list.lua` file:

*   **Categorization by Comments**: Perks are often grouped together using Lua comments (e.g., `-- VARIOUS`, `-- gold / money related`, `-- PLAYER EFFECTS`). This suggests an intended, though not strictly enforced, categorization for readability and organization.
*   **Localization for UI**: All UI-related text (`ui_name`, `ui_description`) uses localization keys (e.g., `$perk_critical_hit`). This allows for easy translation of the game's text.
*   **Scripted Effects**: Many perks utilize `func` and `func_remove` to implement their effects. These functions can interact with various game components, modify entity properties, or trigger other Lua scripts. This demonstrates the highly scriptable nature of Noita's perk system.
*   **Component-Based Modification**: The `func` and `func_remove` functions frequently interact with entity components (e.g., `CharacterPlatformingComponent`, `DamageModelComponent`, `SpriteComponent`, `LuaComponent`). This is a fundamental aspect of how Noita modifies game entities.
*   **Global State Modification**: Some perks, like `UNLIMITED_SPELLS` and `RAT`, modify global game state variables or flags (e.g., `perk_infinite_spells`, `player_status_cordyceps`).
*   **Event Handling**: Perks can trigger or respond to in-game events, as seen with `perk_pickup_event` and `reset_perk_pickup_event`.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `CRITICAL_HIT` Perk:**

```lua
{
    id = "CRITICAL_HIT",
    ui_name = "$perk_critical_hit",
    ui_description = "$perkdesc_critical_hit",
    ui_icon = "data/ui_gfx/perk_icons/critical_hit.png",
    perk_icon = "data/items_gfx/perks/critical_hit.png",
    game_effect = "CRITICAL_HIT_BOOST",
    particle_effect = "critical_hit_boost",
    stackable = STACKABLE_YES,
    usable_by_enemies = true,
},
```
This entry defines a perk that likely increases the chance or damage of critical hits. It has a clear `id`, UI references, icon paths, and a `game_effect` tag. It's stackable and can be used by enemies.

**2. `BREATH_UNDERWATER` Perk:**

```lua
{
    id = "BREATH_UNDERWATER",
    ui_name = "$perk_breath_underwater",
    ui_description = "$perkdesc_breath_underwater",
    ui_icon = "data/ui_gfx/perk_icons/breath_underwater.png",
    perk_icon = "data/items_gfx/perks/breath_underwater.png",
    game_effect = "BREATH_UNDERWATER",
    stackable = STACKABLE_YES,
    stackable_is_rare = true,
    usable_by_enemies = true,
    func = function( entity_perk_item, entity_who_picked, item_name )
        -- ... (code to modify swim buoyancy and drag) ...
        local damage_model = EntityGetFirstComponent( entity_who_picked, "DamageModelComponent" )
        if( damage_model ~= nil ) then
            local air_max = ComponentGetValue( damage_model, "air_in_lungs_max" )
            ComponentSetValue( damage_model, "air_in_lungs", air_max )
        end
    end,
    func_remove = function( entity_who_picked )
        -- ... (code to reset swim parameters) ...
    end,
},
```
This perk grants the ability to breathe underwater. It's stackable, rare, and usable by enemies. Crucially, it includes `func` and `func_remove` functions that directly modify the player's `CharacterPlatformingComponent` to alter swimming physics and the `DamageModelComponent` to set air in lungs.

**3. `UNLIMITED_SPELLS` Perk:**

```lua
{
    id = "UNLIMITED_SPELLS",
    ui_name = "$perk_unlimited_spells",
    ui_description = "$perkdesc_unlimited_spells",
    ui_icon = "data/ui_gfx/perk_icons/unlimited_spells.png",
    perk_icon = "data/items_gfx/perks/unlimited_spells.png",
    stackable = STACKABLE_NO,
    func = function( entity_perk_item, entity_who_picked, item_name )
        local world_entity_id = GameGetWorldStateEntity()
        if( world_entity_id ~= nil ) then
            local comp_worldstate = EntityGetFirstComponent( world_entity_id, "WorldStateComponent" )
            if( comp_worldstate ~= nil ) then
                ComponentSetValue( comp_worldstate, "perk_infinite_spells", "1" )
            end
        end
        GameRegenItemActionsInPlayer( entity_who_picked )
        -- ... (UI refreshing code) ...
    end,
    func_remove = function( entity_who_picked )
        local world_entity_id = GameGetWorldStateEntity()
        if( world_entity_id ~= nil ) then
            local comp_worldstate = EntityGetFirstComponent( world_entity_id, "WorldStateComponent" )
            if( comp_worldstate ~= nil ) then
                ComponentSetValue( comp_worldstate, "perk_infinite_spells", "0" )
            end
        end
        GameRegenItemActionsInPlayer( entity_who_picked )
        -- ... (UI refreshing code) ...
    end,
},
```
This perk makes all spells have unlimited uses. It's not stackable. Its `func` modifies the global `WorldStateComponent` to enable infinite spells and also calls `GameRegenItemActionsInPlayer` to update the player's inventory. The `func_remove` reverses these changes.

## Reference

This file contains 3339 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/perks/perk_list.lua).

---