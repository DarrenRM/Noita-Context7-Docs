---
title: Pata Rocket 6 Projectile
category: scripts
---

# Pata Rocket 6 Projectile

This script defines the behavior for the "Pata Rocket 6" projectile in Noita. It primarily focuses on spawning a visual trail effect upon its creation.

## Key Attributes

### Entity Loading

*   **`EntityLoad`**: This function is used to spawn a new entity at the projectile's position.
    *   **`"data/entities/particles/particle_explosion/explosion_trail_swirl_blue_slow.xml"`**: Specifies the XML file for the particle effect to be loaded. This indicates a blue, slow-moving swirl trail.
    *   **`pos_x`, `pos_y`**: The coordinates where the particle effect will be spawned, matching the projectile's current position.

## Script Logic

The script is straightforward:

1.  **`dofile_once("data/scripts/lib/utilities.lua")`**: Ensures that utility functions are loaded and available.
2.  **`local entity_id = GetUpdatedEntityID()`**: Retrieves the unique identifier for the current entity (the projectile).
3.  **`local pos_x, pos_y = EntityGetTransform( entity_id )`**: Gets the current X and Y coordinates of the projectile.
4.  **`local eid = EntityLoad(...)`**: Spawns the specified particle effect at the projectile's location.

This script's primary purpose is to add a visual flourish to the Pata Rocket 6 projectile by creating a distinct trail effect.