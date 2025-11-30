---
title: Bunker 2 Check Script
category: scripts
---

# Bunker 2 Check Script

This script is responsible for spawning specific entities and actions when a player is within a certain radius and a specific game flag is active. It appears to be related to a "bunker" or "fishing hut" mechanic in the game.

## Core Functionality

The script checks for the presence of a player within a 200-unit radius and if the game flag `"fishing_hut_b"` is set. If both conditions are met, it proceeds to spawn several game elements and then destroys the entity running this script.

## Key Actions Triggered

When the conditions are met, the following actions occur:

### Entity Spawning

*   **Physics Chair:** `data/entities/props/physics_chair_1.xml` is loaded at a relative position `(x - 16, y + 16)`.
*   **Experimental Wand:** `data/entities/items/wands/experimental/experimental_wand_1.xml` is loaded at `(x + 64, y - 32)`.
*   **Temporary Workshop:** `data/entities/buildings/workshop_temporary.xml` is loaded at `(x + 48, y)`.

### Item Action Entity Creation

A series of "Item Action Entities" are created with specific identifiers and relative positions. These likely represent conditional logic or interactive elements within the game.

| Identifier   | Relative X | Relative Y |
| :----------- | :--------- | :--------- |
| `IF_HALF`    | `+ 24`     | `- 8`      |
| `IF_HP`      | `+ 38`     | `- 9`      |
| `IF_PROJECTILE` | `+ 52`     | `- 10`     |
| `IF_ENEMY`   | `+ 66`     | `- 11`     |
| `IF_ELSE`    | `+ 80`     | `- 12`     |
| `IF_ELSE`    | `+ 94`     | `- 13`     |
| `IF_END`     | `+ 108`    | `- 14`     |
| `IF_END`     | `+ 122`    | `- 15`     |

*Note: The commented-out `RESET` action suggests it was a potential feature or an earlier iteration.*

### Script Termination

*   **Entity Kill:** The entity executing this script (`entity_id`) is destroyed using `EntityKill( entity_id )`.

## Conditions for Activation

*   **Player Proximity:** A player unit must be within 200 units of the script's entity.
*   **Game Flag:** The game must have the flag `"fishing_hut_b"` set to true.

## Technical Details

*   **Dependencies:** `dofile_once("data/scripts/lib/utilities.lua")` is required for utility functions.
*   **Entity Identification:** `GetUpdatedEntityID()` retrieves the ID of the entity running the script.
*   **Transform:** `EntityGetTransform( entity_id )` gets the current position (`x`, `y`) of the entity.
*   **Radius Check:** `EntityGetInRadiusWithTag( x, y, 200, "player_unit" )` performs the player proximity check.
*   **Flag Check:** `GameHasFlagRun( "fishing_hut_b" )` checks for the specific game flag.
*   **Entity Loading:** `EntityLoad(filepath, x, y)` is used to spawn new entities.
*   **Item Action Creation:** `CreateItemActionEntity( identifier, x, y )` creates interactive elements.