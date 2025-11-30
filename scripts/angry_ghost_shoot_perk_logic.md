---
title: Angry Ghost Shoot Perk Logic
category: scripts
---

# Angry Ghost Shoot Perk Logic

This script defines the behavior for the "Angry Ghost Shoot" perk in Noita. When a wand is fired, this perk allows associated "angry ghost" entities to fire projectiles.

## Core Functionality

The `wand_fired` function is the primary trigger for this perk. It executes when the player fires a wand.

### Key Attributes and Elements:

*   **`wand_fired( wand_id )`**: The main function that is called when a wand is fired.
    *   `wand_id`: The unique identifier of the wand that was fired.

*   **Projectile Velocity**:
    *   A base `projectile_velocity` of `600` is set.
    *   This velocity is randomized between `550` and `750` for each shot fired by a ghost.

*   **Ghost Identification**:
    *   The script identifies "angry ghost" entities by checking their children and looking for the tag `"angry_ghost"`.

*   **Cooldown Mechanism**:
    *   Each "angry ghost" has a cooldown managed by a `VariableStorageComponent` named `"angry_ghost_cooldown"`.
    *   A ghost can only shoot if its cooldown is `0`.
    *   After shooting, the cooldown is reset to `4` frames.

*   **Projectile Selection**:
    *   The projectile fired by the ghost is determined by a `VariableStorageComponent` named `"angry_ghost_projectile_memory"`.
    *   If this component is not found or is empty, the default projectile `"data/entities/projectiles/deck/light_bullet.xml"` is used.

*   **Projectile Direction and Speed**:
    *   The projectile is fired in the direction the wand is facing.
    *   The `projectile_velocity` is applied to the `vel_x` and `vel_y` components for the `shoot_projectile` function.

### Helper Functions Used:

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Imports utility functions.
*   **`GetUpdatedEntityID()`**: Gets the ID of the entity currently being updated (likely the player or the wand).
*   **`EntityGetAllChildren( entity_id )`**: Retrieves all child entities of a given entity.
*   **`EntityHasTag( v, "angry_ghost" )`**: Checks if an entity has the specified tag.
*   **`EntityGetTransform( entity_id )`**: Gets the position and direction of an entity.
*   **`EntityGetFirstComponent( entity_id, component_type, component_name )`**: Retrieves the first component of a specific type and name from an entity.
*   **`ComponentGetValue2( component, value_name )`**: Gets the value of a specific field within a component.
*   **`SetRandomSeed( x, y )`**: Sets the random seed based on position and frame number for more deterministic randomness.
*   **`Random( min, max )`**: Generates a random number within a specified range.
*   **`ComponentSetValue2( component, value_name, value )`**: Sets the value of a specific field within a component.
*   **`shoot_projectile( entity_id, projectile, pos_x, pos_y, vel_x, vel_y )`**: Spawns a projectile.

This script is a good example of how to implement perk-like behaviors that interact with existing entities and game mechanics in Noita.