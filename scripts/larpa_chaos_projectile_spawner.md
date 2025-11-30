---
title: Larpa Chaos Projectile Spawner
category: scripts
---

# Larpa Chaos Projectile Spawner

This script defines the behavior for a projectile that spawns other projectiles in a chaotic manner. It's designed to be attached to a projectile entity and uses a `VariableStorageComponent` to determine which projectile to spawn.

## Key Functionality

*   **Dynamic Projectile Spawning:** The core function is to spawn a new projectile based on a specified `projectile_file` stored in a `VariableStorageComponent`.
*   **Randomized Direction:** The spawned projectile is launched in a random direction around the spawner.
*   **Tagging:** The spawned projectile is tagged with `"projectile_cloned"` for potential further processing or identification.

## Configuration

The behavior of this script is primarily controlled by a `VariableStorageComponent` attached to the entity.

### VariableStorageComponent

| Variable Name     | Type         | Description                                                              |
| :---------------- | :----------- | :----------------------------------------------------------------------- |
| `projectile_file` | `string`     | The path to the `.lua` file of the projectile to be spawned.             |

## Script Logic

1.  **Initialization:**
    *   Retrieves the root entity ID and its position.
    *   Sets a random seed based on game frame, component ID, and entity position for varied outcomes.

2.  **Projectile File Retrieval:**
    *   Iterates through `VariableStorageComponent`s attached to the entity.
    *   If a component with the name `"projectile_file"` is found, its string value is stored.

3.  **Spawning Logic:**
    *   If a `projectile_file` has been successfully retrieved:
        *   A random angle between 0 and 359 degrees is generated.
        *   A fixed `length` of 10 is used for the initial velocity magnitude.
        *   Velocity components (`vel_x`, `vel_y`) are calculated based on the random angle and length.
        *   The `shoot_projectile_from_projectile` function is called to spawn the specified projectile with the calculated velocity.
        *   The newly spawned projectile entity is tagged with `"projectile_cloned"`.