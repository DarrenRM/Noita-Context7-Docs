---
title: Statue Physics Shot
category: scripts
---

# Statue Physics Shot

This script defines the behavior for a projectile fired by a statue entity, specifically designed to create a burst of spinning green orbs.

## Core Functionality

The primary function `explode()` is responsible for spawning multiple projectile entities in a circular pattern around the statue.

### Key Attributes & Elements

*   **`explode()` function:**
    *   Retrieves the entity's current position.
    *   Implements a cooldown mechanism using `script_wait_frames( entity_id, 10 )` to prevent rapid firing.
    *   Defines the number of projectiles to spawn (`how_many = 8`).
    *   Calculates the angular increment (`angle_inc`) for even distribution.
    *   Sets the velocity magnitude (`length = 10`) for the projectiles.
    *   Sets an offset distance (`dist = 5`) from the statue's position for projectile spawning.
    *   Iterates to spawn each projectile:
        *   Calculates projectile velocity components (`vel_x`, `vel_y`) based on angle.
        *   Calculates projectile spawn position (`newpos_x`, `newpos_y`) with an offset.
        *   Calls `shoot_projectile()` to create the projectile.

*   **`shoot_projectile()`:**
    *   Spawns a projectile entity.
    *   **Projectile Type:** `"data/entities/projectiles/orb_green_spin.xml"` - This specifies the visual and behavioral characteristics of the spawned projectiles.

*   **`collision_trigger()` function:**
    *   This function is designed to be called when a collision occurs.
    *   It directly calls the `explode()` function, initiating the projectile burst upon collision.

## Summary

This script is a straightforward implementation for a projectile-spawning entity. Its main purpose is to create a radial burst of specific projectiles (`orb_green_spin.xml`) with a controlled firing rate and a slight offset from the originating entity. The `collision_trigger` suggests this script is intended for an entity that reacts to collisions by firing.