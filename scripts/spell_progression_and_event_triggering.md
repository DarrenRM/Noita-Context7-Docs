---
title: Spell Progression and Event Triggering
category: scripts
---

# Spell Progression and Event Triggering

This script manages a progression system for spells, triggering specific in-game events based on a "stage" variable. It's designed to be attached to an entity that persists through gameplay, likely a spell component or a dedicated game manager entity.

## Core Functionality

The script primarily focuses on:

1.  **Tracking Progression:** It uses a `VariableStorageComponent` to store and increment an integer `state` variable, representing the current progression stage.
2.  **Displaying Stage Names:** It displays localized names for each stage using `GamePrintImportant`.
3.  **Conditional Entity Spawning:** Based on the current `state`, it loads and spawns various pre-defined entities at specific locations or relative to the player.
4.  **Player Interaction:** It can locate the player and, in some cases, attach spawned entities to the player.

## Key Attributes and Elements

### Variable Storage and State Management

*   **`VariableStorageComponent`**: This component is crucial for storing the `state` variable.
    *   **`name`**: Expected to be `"stage"`.
    *   **`value_int`**: Stores the current integer stage. The script increments this value each time it runs.

### Stage Names

*   **`stage_names` Table**: An array of localized strings that are displayed to the player as the progression advances.
    *   Example entries: `"$item_mcguffin_0"`, `"$item_mcguffin_1"`, etc.

### Conditional Entity Spawning Logic

The script uses a series of `if` statements to check the `state` and trigger corresponding actions.

*   **`state == 1`**: Spawns `data/entities/projectiles/remove_ground.xml`.
*   **`state == 2`**: Spawns `data/entities/projectiles/circle_lava_small.xml` slightly above the current entity's position.
*   **`state == 5`**: Spawns `data/entities/projectiles/circle_acid_small.xml` slightly above the current entity's position.
*   **`state == 6`**: Spawns `data/entities/projectiles/deck/meteor_rain.xml` for each enemy found and attaches them to the respective enemies.
*   **`state == 10`**: Iterates through entities tagged as `"enemy"`. If an enemy does not have the `"necromancer_shop"` or `"boss"` tag, it spawns `data/entities/animals/necromancer_shop.xml` at the enemy's location and then kills the enemy.
*   **`state == 12`**: Spawns `data/entities/projectiles/rain_gold.xml`.
*   **`state == 14`**: Spawns `data/entities/items/pickup/chest_random_super.xml`.

### Player and Enemy Handling

*   **Player Identification**: `EntityGetWithTag("player_unit")` is used to find the player.
*   **Entity Positioning**: If the player is found, the script can set the current entity's transform to the player's position.
*   **Enemy Iteration**: `EntityGetWithTag("enemy")` is used to find all entities tagged as enemies for specific stage events.

## Example Usage (Conceptual)

To use this script, you would typically:

1.  Create an entity in an XML file (e.g., `my_progression_manager.xml`).
2.  Add a `VariableStorageComponent` to this entity, initializing the `"stage"` variable to `0`.
3.  Attach this script to the entity using a `ScriptComponent`.
4.  Ensure this entity is loaded into the game world.

```lua
-- Example of how this script might be attached to an entity
-- In your entity XML:
-- <entity name="progression_manager">
--     <VariableStorageComponent name="stage" value_int="0" />
--     <ScriptComponent script_filename="data/scripts/all_spells_stage.lua" />
-- </entity>
```