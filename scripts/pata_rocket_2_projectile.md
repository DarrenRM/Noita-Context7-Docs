---
title: Pata Rocket 2 Projectile
category: scripts/
---

# Pata Rocket 2 Projectile

This script defines the behavior for the "Pata Rocket 2" projectile in Noita. It primarily focuses on spawning a visual trail effect upon its creation.

## Key Attributes

*   **Entity Loading:** The core functionality is to load a specific particle effect.
    *   `EntityLoad("data/entities/particles/particle_explosion/explosion_trail_swirl_red_slow.xml", pos_x, pos_y)`: This line loads the visual trail effect.
        *   **File:** `data/entities/particles/particle_explosion/explosion_trail_swirl_red_slow.xml` specifies the visual asset.
        *   **Position:** `pos_x`, `pos_y` are the coordinates where the trail will be spawned, matching the projectile's initial position.

## Script Logic

The script is straightforward:

1.  **Include Utilities:** `dofile_once("data/scripts/lib/utilities.lua")` ensures necessary utility functions are available.
2.  **Get Entity ID:** `local entity_id = GetUpdatedEntityID()` retrieves the unique identifier for the projectile entity.
3.  **Get Position:** `local pos_x, pos_y = EntityGetTransform( entity_id )` obtains the projectile's current X and Y coordinates.
4.  **Spawn Trail Effect:** `local eid = EntityLoad(...)` creates the visual trail particle effect at the projectile's location.

This script is a simple example of how projectiles can be configured to have visual effects associated with their spawning.