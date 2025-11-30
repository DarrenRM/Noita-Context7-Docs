---
title: Larpa Chaos Projectile Script
category: scripts
---

# Larpa Chaos Projectile Script

This script defines the behavior for the "Larpa Chaos" projectile in Noita. When this projectile is spawned, it randomly selects another projectile from its configuration and fires it in a random direction.

## Key Functionality

*   **Random Projectile Selection:** The script reads a `projectile_file` variable from a `VariableStorageComponent` attached to the entity. This variable specifies the file path of the projectile to be spawned.
*   **Random Directional Firing:** Upon activation, the script calculates a random angle and then determines the velocity components (`vel_x`, `vel_y`) to fire the selected projectile in that direction.
*   **Cloning Tag:** The spawned projectile is given the tag `"projectile_cloned"` for potential further processing or identification.

## Core Attributes

The behavior of this script is primarily controlled by the `VariableStorageComponent` attached to the projectile entity.

### VariableStorageComponent

This component holds the configuration for which projectile to spawn.

| Attribute      | Type   | Description                                                                 |
| :------------- | :----- | :-------------------------------------------------------------------------- |
| `name`         | string | Must be set to `"projectile_file"` to be recognized by this script.       |
| `value_string` | string | The file path of the projectile to be spawned (e.g., `"data/projectiles/fireball.lua"`). |

## Script Logic Breakdown

1.  **Initialization:**
    *   Retrieves the root entity ID and its position (`pos_x`, `pos_y`).
    *   Sets a random seed based on game frame and entity properties to ensure varied outcomes.

2.  **Projectile File Retrieval:**
    *   Iterates through all `VariableStorageComponent`s attached to the entity.
    *   If a component's `name` is `"projectile_file"`, its `value_string` is stored in the `projectile_file` variable.

3.  **Projectile Spawning:**
    *   If `projectile_file` is not empty:
        *   A random `angle` between 0 and 359 degrees is generated.
        *   A `length` of 1500 is used as the magnitude for the velocity.
        *   `vel_x` and `vel_y` are calculated based on the random angle and length.
        *   The `shoot_projectile_from_projectile` function is called to spawn the projectile specified by `projectile_file` at the current position with the calculated velocity.
        *   The newly spawned projectile's entity ID (`eid`) is retrieved.
        *   The tag `"projectile_cloned"` is added to the spawned projectile.

## Example Usage

To make this script spawn a "fireball" projectile, you would attach a `VariableStorageComponent` to the "Larpa Chaos" projectile entity with the following configuration:

```lua
VariableStorageComponent.name = "projectile_file"
VariableStorageComponent.value_string = "data/projectiles/fireball.lua"
```