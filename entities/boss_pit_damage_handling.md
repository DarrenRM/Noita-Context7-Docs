---
title: Boss Pit Damage Handling
category: entities
---

---

# Boss Pit Damage Handling

This document details the Lua script responsible for handling damage reception by the Boss Pit entity in Noita. It focuses on modifying its invincibility, damage multipliers, and projectile firing behavior.

## Core Functionality

The primary function `damage_received` is triggered when the Boss Pit entity takes damage.

### Key Actions:

*   **Invincibility Activation:** Immediately after receiving damage, the entity is set to be invincible.
*   **Damage Multiplier Reset:** The `HitboxComponent`'s `damage_multiplier` is set to `0.0`, effectively making it immune to further direct damage from this instance.
*   **Randomized Projectile Firing:** A chance-based system determines if the Boss Pit will fire a projectile. This involves:
    *   Retrieving and modifying a "state" variable from its `VariableStorageComponent`.
    *   Potentially updating a "memory" variable, which dictates the type of projectile to be fired.
    *   Spawning a projectile using `shoot_projectile` with randomized velocity and angle.
    *   Configuring the spawned projectile's `VariableStorageComponent` with the determined projectile type.

## Key Components and Attributes

This script interacts with and modifies specific components of the Boss Pit entity.

### `HitboxComponent`

*   **`damage_multiplier`**: This attribute is set to `0.0` upon receiving damage, rendering the entity temporarily immune to further damage.

### `VariableStorageComponent`

This component is crucial for managing the Boss Pit's state and projectile behavior.

*   **`name`**:
    *   **`state`**: An integer value that cycles through states (0-9) using the modulo operator. This likely influences internal behavior or visual cues.
    *   **`memory`**: A string value that stores the path to the projectile XML file to be fired. If empty, it defaults to `"data/entities/projectiles/enlightened_laser_darkbeam.xml"`.
*   **`value_int`**: Stores the integer value for the `state` variable.
*   **`value_string`**: Stores the string value for the `memory` variable.

### `EntityGetComponent` and `EntitySetComponentsWithTagEnabled`

These functions are used to access and modify entity components and their properties.

*   **`EntityGetComponent( entity_id, "VariableStorageComponent" )`**: Retrieves all `VariableStorageComponent` instances attached to the entity.
*   **`EntitySetComponentsWithTagEnabled( entity_id, "invincible", true )`**: Enables the "invincible" tag for the entity, making it immune to damage.

## Projectile Firing Logic

The script includes a randomized mechanism for firing projectiles.

### `shoot_projectile`

*   **`entity_id`**: The ID of the entity that is firing the projectile.
*   **`"data/entities/animals/boss_pit/wand.xml"`**: The XML file defining the projectile's origin or "wand".
*   **`x, y`**: The spawn coordinates of the projectile.
*   **`vel_x, vel_y`**: The velocity components of the projectile, calculated based on a random angle.

### Randomization

*   **`SetRandomSeed( x, y * GameGetFrameNum() )`**: Seeds the random number generator based on the entity's position and the current frame number for more varied outcomes.
*   **`Random( 1, 3 ) == 1`**: A 1 in 3 chance to trigger the projectile firing sequence.
*   **`Random( 1, 200 ) * math.pi`**: Generates a random angle for projectile trajectory.