---
title: Moon Altar Extra Logic
category: scripts
---

# Moon Altar Extra Logic

This script defines the behavior for a special "Moon Altar" entity in Noita, triggering specific effects when certain conditions are met.

## Core Functionality

The primary function of this script is to check for the presence of all four elemental essences and a specific target entity. If all conditions are satisfied, it applies a persistent flag, spawns several "touch" item action entities, loads a visual effect, prints a message to the player, and then destroys itself.

## Key Conditions and Triggers

### Essence Requirements

The altar requires the player to have collected all four elemental essences:

*   `essence_fire`
*   `essence_air`
*   `essence_water`
*   `essence_laser`

These are checked using `GameHasFlagRun()`.

### Target Entity

A specific target entity must also be present. The script looks for entities with the tag obtained from `get_flag_name( "u_dheglmticg" )`.

### Player Proximity

The player unit must be within a radius of 48 units from the altar. This is checked using `EntityGetInRadiusWithTag()`.

## Triggered Effects

When all conditions are met, the following effects occur:

### Persistent Flag

A persistent flag is added to the game state, identified by `get_flag_name( "bqedcjkvxooa" )`.

### Item Action Entities

Several "touch" item action entities are spawned around the altar's position. These likely interact with the player or environment upon touch:

*   `TOUCH_GOLD`
*   `TOUCH_WATER`
*   `TOUCH_OIL`
*   `TOUCH_ALCOHOL`
*   `TOUCH_BLOOD`
*   `TOUCH_SMOKE`

### Visual Effect

A visual effect entity is loaded at the altar's position:

*   `data/entities/misc/moon_effect_test.xml`

### Player Notification

An important message is displayed to the player using `GamePrintImportant()` with the following localization keys:

*   `$log_moon_altar_extra`
*   `$logdesc_moon_altar_extra`

### Self-Destruction

The Moon Altar entity itself is destroyed using `EntityKill( entity_id )` after its effects are triggered.

## Script Structure

The script follows a standard Lua structure for Noita entities:

1.  **Initialization:**
    *   Includes utility functions.
    *   Retrieves the current entity's ID and transform (position).
    *   Fetches flag names for target entity identification.
    *   Checks for the presence of all four essences.
2.  **Target and Proximity Checks:**
    *   Finds entities with the specific target tag.
    *   Finds the player unit within a radius.
3.  **Conditional Execution:**
    *   An `if` statement combines all the checks (essences, target entity, player proximity).
4.  **Effect Application:**
    *   If the conditions are met, the effects described above are executed.
5.  **Cleanup:**
    *   The altar entity is killed.