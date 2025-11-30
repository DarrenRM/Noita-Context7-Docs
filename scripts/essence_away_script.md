---
title: Essence Away Script
category: scripts
---

# Essence Away Script

This script handles the removal and potential conversion of "essence" effects when the player dies or a specific game event occurs. It's designed to clean up lingering essence pickups and potentially spawn new items based on collected essences.

## Core Functionality

The primary function, `death()`, is triggered by a game event (likely player death). Its main responsibilities are:

1.  **Removing Essence Effects:** It iterates through the player's children entities to find and remove any tagged with `essence_effect`.
2.  **Counting Picked Essences:** It retrieves global variables that track the counts of various "essence" pickups (Laser, Fire, Water, Air, Alcohol).
3.  **Spawning New Items:** Based on the counts of picked essences, it loads specific item entities (e.g., `stonestone.xml`, `brimstone.xml`) at the player's death location.
4.  **Resetting Essence Flags:** It removes global flags related to active essence effects.
5.  **Visual/Audio Feedback:** If essence effects were removed (`doit` is true), it spawns a particle effect and plays a sound, along with a game message.

## Key Functions and Variables

### `death()`

This is the main function executed by the game.

*   **Entity Management:**
    *   `GetUpdatedEntityID()`: Gets the ID of the entity that triggered the script.
    *   `EntityGetTransform( entity_id )`: Retrieves the position (x, y) of an entity.
    *   `EntityGetWithTag( "player_unit" )`: Finds all entities with the tag "player\_unit".
    *   `EntityGetAllChildren( v )`: Gets all child entities of a given entity.
    *   `EntityHasTag( b, "essence_effect" )`: Checks if an entity has a specific tag.
    *   `EntityRemoveFromParent( b )`: Removes an entity from its parent.
    *   `EntityKill( b )`: Destroys an entity.
    *   `EntityLoad( v, x, y )`: Loads an entity at a specified position.

*   **Global Variable Management:**
    *   `GlobalsGetValue( key, default )`: Retrieves the value of a global variable, with a default if it doesn't exist.
    *   `GlobalsSetValue( key, value )`: Sets the value of a global variable.
    *   `GameRemoveFlagRun( flag_name )`: Removes a global game flag.

*   **Game Feedback:**
    *   `print( ... )`: Logs messages to the console (useful for debugging).
    *   `GamePrintImportant( message_key, description_key )`: Displays an important message to the player.
    *   `GamePlaySound( bank, sound_name, x, y )`: Plays a sound effect at a specific location.

### Global Variable Keys (Essence Counts)

These keys are used to store and retrieve the number of each type of essence picked up.

| Key Name                      | Description                               |
| :---------------------------- | :---------------------------------------- |
| `ESSENCE_LASER_PICKUP_COUNT`  | Count of Laser essence pickups.           |
| `ESSENCE_FIRE_PICKUP_COUNT`   | Count of Fire essence pickups.            |
| `ESSENCE_WATER_PICKUP_COUNT`  | Count of Water essence pickups.           |
| `ESSENCE_AIR_PICKUP_COUNT`    | Count of Air essence pickups.             |
| `ESSENCE_ALCOHOL_PICKUP_COUNT`| Count of Alcohol essence pickups.         |

### Item Spawning Logic

The script dynamically creates a `loadlist` based on the `pick` counts. Each picked essence adds a corresponding item XML to this list.

| Picked Essence Type | Item XML to Load                     |
| :------------------ | :----------------------------------- |
| Laser (`pick1`)     | `data/entities/items/pickup/stonestone.xml` |
| Fire (`pick2`)      | `data/entities/items/pickup/brimstone.xml`  |
| Water (`pick3`)     | `data/entities/items/pickup/waterstone.xml` |
| Air (`pick4`)       | `data/entities/items/pickup/thunderstone.xml`|
| Alcohol (`pick5`)   | `data/entities/items/pickup/poopstone.xml`  |

The spawned items are placed vertically, with a small offset to prevent overlap.

### Game Flags Removed

The following game flags are removed to signify the end of the essence effects:

*   `essence_laser`
*   `essence_fire`
*   `essence_water`
*   `essence_air`
*   `essence_alcohol`

### Visual and Audio Effects

If any `essence_effect` entities were removed (`doit == true`):

*   **Particle Effect:** `data/entities/particles/image_emitters/perk_effect.xml` is spawned.
*   **Sound Effect:** `data/audio/Desktop/projectiles.bank`, sound `player_projectiles/megalaser/launch` is played.
*   **Game Message:** `"$log_curse_secret"` and `"$logdesc_curse_fade"` are displayed.