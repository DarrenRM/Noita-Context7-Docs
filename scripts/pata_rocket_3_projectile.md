---
title: Pata Rocket 3 Projectile
category: scripts/
---

# Pata Rocket 3 Projectile

This script defines the behavior of the "Pata Rocket 3" projectile in Noita. It primarily focuses on spawning a visual trail effect upon its creation.

## Key Attributes

*   **Entity Loading:** The script's main function is to load a specific particle effect.
    *   `EntityLoad("data/entities/particles/particle_explosion/explosion_trail_swirl_green_slow.xml", pos_x, pos_y)`: This line is responsible for spawning the visual trail. It references an external XML file for the particle's appearance and behavior.

## Script Logic

1.  **Initialization:**
    *   `dofile_once("data/scripts/lib/utilities.lua")`: Includes utility functions, likely for common game operations.
    *   `local entity_id = GetUpdatedEntityID()`: Retrieves the unique identifier for the projectile entity.
    *   `local pos_x, pos_y = EntityGetTransform(entity_id)`: Gets the current X and Y coordinates of the projectile.

2.  **Particle Spawning:**
    *   `local eid = EntityLoad(...)`: Loads the specified particle effect at the projectile's current position. This creates the visual "swirl green slow" trail.

## AI Modding Considerations

*   **Visual Effects:** To modify the visual trail, you would need to edit the referenced XML file (`data/entities/particles/particle_explosion/explosion_trail_swirl_green_slow.xml`).
*   **Projectile Behavior:** This script *only* handles the initial visual trail. Any actual projectile movement, damage, or explosion logic would be defined in other scripts or entity components associated with the "Pata Rocket 3" projectile.