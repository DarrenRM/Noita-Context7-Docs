---
title: All Spells Projectile Initialization
category: scripts
---

---

# All Spells Projectile Initialization

This script initializes a cluster of projectiles, likely for a spell that disperses multiple smaller projectiles. It calculates their positions and angles based on the caster's position and a frame-dependent offset.

## Key Attributes and Elements

### Projectile Spawning Logic

*   **`how_many`**: Determines the number of projectiles to spawn.
*   **`angle_inc`**: Calculates the angular increment between spawned projectiles to ensure even distribution.
*   **`theta`**: The initial angle for the first projectile, influenced by game frames for dynamic rotation.
*   **`length`**: The distance from the caster at which projectiles are spawned.
*   **`shoot_projectile_from_projectile`**: The core function used to spawn new projectiles, referencing an XML entity definition (`all_spells_part.xml`).

### Projectile Customization (via `VariableStorageComponent`)

Each spawned projectile is assigned several variables to customize its behavior:

*   **`angle`**: Stores the projectile's initial angle.
*   **`rot`**: Stores a random rotation value for the projectile.
*   **`owner`**: Stores the `entity_id` of the projectile's caster.
*   **`length`**: Stores a specific length value for the projectile (appears to be fixed at 8.0 in this script).

### Initialization Process

1.  **Get Caster Information**: Retrieves the `entity_id` and position (`pos_x`, `pos_y`) of the entity casting this script.
2.  **Calculate Spawning Parameters**: Determines the number of projectiles, angular separation, and initial angle.
3.  **Random Seed**: Sets a random seed based on the game frame and caster position for varied results.
4.  **Loop and Spawn**: Iterates `how_many` times:
    *   Calculates the `new_x` and `new_y` coordinates for the projectile based on `theta` and `length`.
    *   Spawns a new projectile using `shoot_projectile_from_projectile`.
    *   Adds `VariableStorageComponent` to the spawned projectile to store its `angle`, `rot`, `owner`, and `length`.
    *   Updates `theta` for the next projectile.