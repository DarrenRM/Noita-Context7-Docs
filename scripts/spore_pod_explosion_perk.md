---
title: Spore Pod Explosion Perk
category: scripts
---

---

# Spore Pod Explosion Perk

This script defines the behavior for the "Spore Pod Explosion" perk in Noita. When this perk is active, it causes a projectile to spawn multiple smaller projectiles (spore pods) upon impact or destruction.

## Key Functionality

The core of this script involves iterating a set number of times to create and launch new projectiles.

### Projectile Spawning

*   **`shoot_projectile_from_projectile`**: This is the primary function used to spawn new projectiles. It takes the ID of the originating projectile, the XML file path of the projectile to spawn, and its initial position and velocity.
*   **Number of Spores**: The script spawns **20** individual spore projectiles.
*   **Spore Projectile Type**: The spawned projectiles are of the type defined in `data/entities/misc/perks/spore_pod_spike.xml`.

### Randomization

*   **Velocity**: The `vel_x` and `vel_y` for each spawned spore are randomized within the range of **-100 to 100**. This ensures a spread of projectiles in various directions.
*   **Seed**: The random seed is set using the entity's position (`x`, `y`) and the current game frame number (`GameGetFrameNum()`) to ensure a consistent, yet unique, spread for each instance of the perk activation.

## Technical Details

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Imports utility functions, likely including `shoot_projectile_from_projectile`.
*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the entity that triggered this script.
*   **`EntityGetTransform( entity_id )`**: Gets the current position (`x`, `y`) of the entity.
*   **`SetRandomSeed( x * entity_id, y + GameGetFrameNum() )`**: Initializes the random number generator for this specific instance.
*   **`Random( min, max )`**: Generates a random floating-point number within the specified range.