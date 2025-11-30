---
title: Bomb Detonator Projectile Logic
category: scripts
---

# Bomb Detonator Projectile Logic

This script defines the behavior of a "bomb detonator" projectile in Noita. Its primary function is to detonate other projectiles that share the same owner and meet specific explosion criteria.

## Core Functionality

The script iterates through all entities tagged as "projectile". For each projectile found, it checks if it shares the same owner (`mWhoShot`) as the detonator projectile. If they are owned by the same entity, and the target projectile is set to explode on death, on lifetime out, or has an explosion radius greater than 2, the target projectile is then forced to explode and is subsequently killed.

## Key Components and Attributes

This script primarily interacts with `ProjectileComponent` to determine ownership and explosion properties.

### ProjectileComponent Attributes Used:

*   **`mWhoShot`**: Identifies the entity that created the projectile. Used to ensure only projectiles from the same owner are affected.
*   **`on_death_explode`**: A boolean flag. If `true`, the projectile will explode when it dies.
*   **`on_lifetime_out_explode`**: A boolean flag. If `true`, the projectile will explode when its lifetime expires.
*   **`config_explosion`**: A table containing explosion configuration.
    *   **`explosion_radius`**: The radius of the explosion. A value greater than 2 triggers detonation.

## Script Logic Breakdown

1.  **Initialization**:
    *   Loads utility functions.
    *   Gets the unique ID of the current detonator entity.
    *   Retrieves the `ProjectileComponent` of the detonator.

2.  **Projectile Iteration**:
    *   Fetches all entities with the tag "projectile".
    *   If there are any projectiles and the detonator has a `ProjectileComponent`:
        *   Loops through each found projectile.
        *   Retrieves the `ProjectileComponent` of the current projectile in the loop.

3.  **Ownership and Explosion Check**:
    *   If the looped projectile has a `ProjectileComponent` and is not the detonator itself:
        *   Compares the `mWhoShot` values of the detonator and the looped projectile.
        *   Checks the `on_death_explode`, `on_lifetime_out_explode`, and `config_explosion.explosion_radius` of the looped projectile.

4.  **Detonation Trigger**:
    *   If the `mWhoShot` values match AND any of the explosion conditions (`on_death_explode` is true, `on_lifetime_out_explode` is true, or `explosion_radius` > 2) are met:
        *   Forces the looped projectile to explode by setting `on_death_explode` and `on_lifetime_out_explode` to `true`.
        *   Kills the looped projectile using `EntityKill()`.