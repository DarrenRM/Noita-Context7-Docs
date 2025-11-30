---
title: All Spells Loader Projectile Script
category: scripts
---

---

# All Spells Loader Projectile Script

This script defines the behavior for a projectile that acts as a loader for "all spells" in Noita. When this projectile is active, it attempts to spawn other projectiles from the `all_spells_loader.xml` entity, distributing them randomly around nearby players.

## Key Functionality

*   **Player Targeting:** Identifies all entities tagged as "player_unit".
*   **Randomized Spawning:** For each player found, it calculates a random offset (within a 48x48 pixel area) from the player's position.
*   **Projectile Creation:** Spawns a new projectile using `shoot_projectile_from_projectile`. The spawned projectile is `data/entities/projectiles/deck/all_spells_loader.xml`.
*   **In-Game Notification:** Displays an important message to the player using `GamePrintImportant` with the keys "$log_all_spells" and "$logdesc_all_spells".

## Core Attributes & Elements

*   `dofile_once("data/scripts/lib/utilities.lua")`: Imports utility functions.
*   `GetUpdatedEntityID()`: Retrieves the unique identifier for the current projectile entity.
*   `EntityGetTransform( entity_id )`: Gets the position (x, y) of the projectile.
*   `EntityGetWithTag( "player_unit" )`: Returns a list of all entities with the "player_unit" tag.
*   `SetRandomSeed( pos_x, pos_y )`: Initializes the random number generator based on the projectile's position for more deterministic randomness within a given context.
*   `Random( 0, 1 )`: Generates a random float between 0 and 1.
*   `shoot_projectile_from_projectile( projectile_entity_id, projectile_xml_path, target_x, target_y, velocity_x, velocity_y )`: The core function for spawning new projectiles.
    *   `projectile_entity_id`: The ID of the projectile initiating the spawn.
    *   `projectile_xml_path`: The XML path to the entity definition of the projectile to be spawned.
    *   `target_x`, `target_y`: The world coordinates where the new projectile will be spawned.
    *   `velocity_x`, `velocity_y`: The initial velocity of the spawned projectile.
*   `GamePrintImportant( message_key, description_key )`: Displays a significant message to the player.

## Example Usage (Conceptual)

This script is typically attached to a projectile entity that is itself spawned by a spell. When that initial spell projectile hits something or expires, this script executes, leading to the spawning of multiple "all spells loader" projectiles around players.