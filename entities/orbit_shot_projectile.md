---
title: Orbit Shot Projectile
category: entities
---

# Orbit Shot Projectile

This entity defines a projectile that orbits its target. It utilizes two Lua components to manage its behavior.

## Core Components

### `LuaComponent` (Initialization)

This component is responsible for the initial setup and behavior of the orbiting projectile.

*   **`script_source_file`**: `data/scripts/projectiles/orbit_shot_init.lua`
    *   This script handles the initial logic for the orbiting shot.
*   **`execute_every_n_frame`**: `2`
    *   The initialization script runs every 2 frames.
*   **`remove_after_executed`**: `1`
    *   This component is removed after its script has executed once.

### `LuaComponent` (Orbiting Logic)

This component manages the continuous orbiting behavior of the projectile.

*   **`script_source_file`**: `data/scripts/projectiles/orbit_shot.lua`
    *   This script contains the core logic for the projectile's orbit.
*   **`execute_every_n_frame`**: `1`
    *   The orbiting script runs every frame to update the projectile's position and behavior.

## Key Concepts for Modding

*   **Orbiting Mechanics**: The core of this entity's functionality lies within the `orbit_shot.lua` script. Modders can modify this script to alter the orbiting speed, radius, target acquisition, and any other orbital behaviors.
*   **Initialization**: The `orbit_shot_init.lua` script is crucial for setting up the projectile when it's spawned. This could include defining initial velocity, target, or any special effects upon creation.
*   **Projectile Behavior**: As a projectile entity, this can be further customized by adding other standard projectile components (e.g., `DamageListComponent`, `VelocityComponent`, `ParticleEmitterComponent`) to modify its damage, speed, visual effects, etc.