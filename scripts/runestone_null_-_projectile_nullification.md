---
title: Runestone Null - Projectile Nullification
category: scripts
---

# Runestone Null - Projectile Nullification

This script implements the functionality of the "Runestone Null" item in Noita. When activated, it targets nearby projectiles and nullifies their explosive properties, preventing them from detonating upon death or when their lifetime expires. It also spawns a visual particle effect at the projectile's location before destroying it.

## Key Functionality

*   **Projectile Targeting:** Scans for entities tagged as "projectile" within a radius of 192 units around the runestone's position.
*   **Explosion Prevention:** Iterates through found projectiles and disables their `on_death_explode` and `on_lifetime_out_explode` properties.
*   **Visual Effect:** Spawns a particle effect (`data/entities/particles/runestone_null.xml`) at the location of each nullified projectile.
*   **Projectile Destruction:** Terminates the targeted projectiles.

## Core Logic Breakdown

The script performs the following steps:

1.  **Initialization:**
    *   Loads utility functions.
    *   Retrieves the entity ID and transform (position) of the runestone itself.

2.  **Projectile Detection:**
    *   Uses `EntityGetInRadiusWithTag` to find all entities with the "projectile" tag within a 192-unit radius.

3.  **Projectile Processing (if projectiles are found):**
    *   Iterates through each detected projectile.
    *   Retrieves the projectile's transform (position).
    *   Fetches the `ProjectileComponent` and `VelocityComponent` for the projectile.
    *   **Nullification:** If `ProjectileComponent` is found, it iterates through its components and sets `on_death_explode` and `on_lifetime_out_explode` to `"0"` (effectively disabling them).
    *   **Visual Spawning:** Loads the `runestone_null.xml` particle effect at the projectile's current position using `EntityLoad`.
    *   **Projectile Removal:** Destroys the projectile using `EntityKill`.

## Key Components and Attributes Modified

*   **`ProjectileComponent`**:
    *   `on_death_explode`: Set to `"0"` to prevent explosion on death.
    *   `on_lifetime_out_explode`: Set to `"0"` to prevent explosion when lifetime expires.

## Related Assets

*   **Particle Effect:** `data/entities/particles/runestone_null.xml` - This XML file defines the visual effect spawned when a projectile is nullified.