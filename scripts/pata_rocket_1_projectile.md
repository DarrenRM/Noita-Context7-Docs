---
title: Pata Rocket 1 Projectile
category: scripts
---

# Pata Rocket 1 Projectile

This script defines the behavior for the "Pata Rocket 1" projectile in Noita. It primarily handles the visual trail effect upon projectile creation.

## Key Attributes

### Entity Loading
This script's main function is to load a specific particle effect when the projectile is spawned.

*   **`EntityLoad`**: This function is used to instantiate an entity at a given position.
    *   **`"data/entities/particles/particle_explosion/explosion_trail_swirl_purple_slow.xml"`**: The XML file defining the visual particle effect for the projectile's trail.
    *   **`pos_x`, `pos_y`**: The coordinates where the particle effect will be spawned, matching the projectile's initial position.

## Script Logic

The script is straightforward:

1.  **`dofile_once("data/scripts/lib/utilities.lua")`**: Includes utility functions, though none are explicitly used in this minimal example.
2.  **`local entity_id = GetUpdatedEntityID()`**: Retrieves the unique identifier for the current entity (the projectile).
3.  **`local pos_x, pos_y = EntityGetTransform( entity_id )`**: Gets the current position of the projectile.
4.  **`local eid = EntityLoad(...)`**: Loads the specified particle effect at the projectile's position.

## Summary

This script is a simple example of how to attach visual effects to projectiles. It leverages `EntityLoad` to create a particle trail, enhancing the visual feedback for the "Pata Rocket 1".