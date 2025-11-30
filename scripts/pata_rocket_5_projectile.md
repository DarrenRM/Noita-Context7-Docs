---
title: Pata Rocket 5 Projectile
category: scripts
---

# Pata Rocket 5 Projectile

This script defines the behavior for the "Pata Rocket 5" projectile in Noita. It primarily focuses on spawning a visual trail effect upon its creation.

## Key Attributes

*   **`entity_id`**: The unique identifier for the projectile entity.
*   **`pos_x`, `pos_y`**: The X and Y coordinates of the projectile's position.

## Core Functionality

The script's main purpose is to load and place a specific particle effect at the projectile's location.

### Particle Effect Spawning

*   **`EntityLoad("data/entities/particles/particle_explosion/explosion_trail_swirl_orange_slow.xml", pos_x, pos_y)`**: This function is called to load and instantiate the particle effect defined in `explosion_trail_swirl_orange_slow.xml` at the projectile's current position. This creates a visual trail for the rocket.