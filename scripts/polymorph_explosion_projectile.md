---
title: Polymorph Explosion Projectile
category: scripts
---

# Polymorph Explosion Projectile

This script defines the behavior for a projectile that creates a "polymorph explosion" effect.

## Core Functionality

The primary purpose of this script is to:

*   **Destroy the projectile:** The `GetUpdatedEntityID()` and subsequent actions imply the projectile itself is consumed or removed after its effect.
*   **Spawn a particle effect:** It loads a specific particle entity (`polymorph_explosion.xml`) at the projectile's current position.

## Key Attributes/Elements

*   **`entity_id`**: Retrieves the unique identifier for the projectile entity.
*   **`pos_x`, `pos_y`**: Gets the current X and Y coordinates of the projectile.
*   **`EntityLoad("data/entities/particles/polymorph_explosion.xml", pos_x, pos_y)`**: This is the core function call. It instantiates the particle effect defined in `polymorph_explosion.xml` at the projectile's location.

## Associated Files

*   **`data/entities/particles/polymorph_explosion.xml`**: This XML file defines the visual and behavioral aspects of the polymorph explosion particle effect itself.

## Usage Notes

This script is a simple projectile that acts as a trigger for a visual effect. It doesn't appear to have complex damage, status effect, or interaction logic beyond spawning the particle.