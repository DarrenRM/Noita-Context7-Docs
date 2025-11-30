---
title: Boss Wizard Debuff Spawner
category: entities
---

---

# Boss Wizard Debuff Spawner

This entity is responsible for applying a random debuff effect to the player when triggered by the Boss Wizard.

## Core Functionality

*   **Random Debuff Application:** Selects a random debuff from a predefined list and spawns its corresponding entity.
*   **UI Feedback:** Plays a sound and displays a localized message indicating the debuff applied.
*   **Self-Destruction:** The spawner entity is removed after its task is completed.

## Key Attributes

*   **`effects` Table:** A Lua table containing the names of debuff entities to be spawned.
    *   `"effect_confusion_ui"`
    *   `"effect_drunk_ui"`
    *   `"effect_hearty"`
    *   `"effect_movement_slower_ui"`
    *   `"effect_twitchy"`
    *   `"effect_weaken"`
    *   `"effect_wither"`
    *   `"effect_homing_shooter"`

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua") -- Loads utility functions.

local entity_id = GetUpdatedEntityID() -- Gets the unique ID of this entity.
local root_entity = EntityGetRootEntity( entity_id ) -- Gets the root entity this spawner belongs to.
local x,y = EntityGetTransform( entity_id ) -- Gets the position of the spawner.

local effects = { -- Defines the list of possible debuff entities.
    "effect_confusion_ui",
    "effect_drunk_ui",
    "effect_hearty",
    "effect_movement_slower_ui",
    "effect_twitchy",
    "effect_weaken",
    "effect_wither",
    "effect_homing_shooter"
}

SetRandomSeed( GameGetFrameNum(), entity_id ) -- Seeds the random number generator for consistent randomness.

local rnd = Random( 1, #effects ) -- Selects a random index from the 'effects' table.

local eid = EntityLoad( "data/entities/misc/" .. effects[rnd] .. ".xml" ) -- Loads the XML for the chosen debuff entity.
EntityAddChild( root_entity, eid ) -- Adds the spawned debuff entity as a child of the root entity.

GamePlaySound( "data/audio/Desktop/projectiles.bank", "player_projectiles/megalaser/launch", x, y ) -- Plays a sound effect.
GamePrint( "$boss_wizard_" .. tostring(rnd) ) -- Displays a localized message to the player, indicating the debuff.

EntityKill( entity_id ) -- Removes the debuff spawner entity from the game.
```