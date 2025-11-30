---
title: Projectile Transformation - Disc Bullets
category: scripts
---

# Projectile Transformation - Disc Bullets

This script modifies existing projectiles, specifically targeting those that are *not* tagged as "disc_bullet_big". It transforms them into "disc_bullet_big" projectiles, inheriting their original position and velocity.

## Core Functionality

The script iterates through all entities tagged as "projectile". For each projectile that *doesn't* have the "disc_bullet_big" tag, it performs the following actions:

1.  **Disables Explosions:** It explicitly sets `on_death_explode` and `on_lifetime_out_explode` to "0" for the projectile's `ProjectileComponent`. This prevents the original projectile from exploding upon death or expiration.
2.  **Captures Velocity:** It retrieves the current velocity (`vel_x`, `vel_y`) of the projectile using its `VelocityComponent`.
3.  **Transforms Projectile:** It uses the `shoot_projectile_from_projectile` function to create a new projectile of type `data/entities/projectiles/deck/disc_bullet_big.xml` at the original projectile's position and with its captured velocity.
4.  **Kills Original Projectile:** The original projectile is then destroyed using `EntityKill`.

## Key Components and Attributes

### `ProjectileComponent`

This component governs the behavior of projectiles. The script specifically targets these attributes:

*   `on_death_explode`: Controls whether the projectile explodes when it dies. Set to `"0"` to disable.
*   `on_lifetime_out_explode`: Controls whether the projectile explodes when its lifetime expires. Set to `"0"` to disable.

### `VelocityComponent`

This component defines the projectile's movement. The script reads the following attribute:

*   `mVelocity`: A `Vector2` value representing the projectile's current velocity.

### `shoot_projectile_from_projectile` Function

This utility function is crucial for creating new projectiles based on existing ones. Its key parameters are:

*   `projectile_id`: The ID of the projectile to base the new one on.
*   `projectile_xml_path`: The XML file path defining the new projectile type (e.g., `"data/entities/projectiles/deck/disc_bullet_big.xml"`).
*   `px`, `py`: The X and Y coordinates for the new projectile's spawn position.
*   `vel_x`, `vel_y`: The X and Y components of the new projectile's initial velocity.

## Usage Context

This script is likely intended to be attached to an entity that spawns or interacts with projectiles, effectively converting a stream of generic projectiles into a specific type of "disc bullet" projectile. This could be used for unique spell effects or enemy behaviors.