---
title: Ultimate Killer Explosion Projectile
category: entities
---

# Ultimate Killer Explosion Projectile

This document details the configuration of the `ultimate_killer_explosion.xml` entity, which defines a powerful projectile designed to cause a large, damaging explosion upon death or collision.

## Core Entity Configuration

The projectile is based on `data/entities/base_projectile.xml`, inheriting its fundamental projectile properties.

### Base Projectile Settings

*   **`gravity_y`**: `100` - Applies a moderate downward gravitational pull to the projectile.

## Projectile Component

This component governs the behavior and effects of the projectile.

### Key Projectile Attributes

*   **`_enabled`**: `1` - Ensures the projectile component is active.
*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Defines the minimum and maximum lob angle, influencing its trajectory.
*   **`speed_min` / `speed_max`**: `160` / `170` - Sets the projectile's initial speed range.
*   **`on_death_explode`**: `1` - Triggers an explosion when the projectile's lifetime ends or it dies.
*   **`on_death_gfx_leave_sprite`**: `0` - Prevents the projectile's sprite from lingering after death.
*   **`on_lifetime_out_explode`**: `1` - Ensures an explosion occurs when the projectile's lifetime expires.
*   **`explosion_dont_damage_shooter`**: `0` - The explosion *can* damage the entity that fired it.
*   **`die_on_low_velocity`**: `1` - The projectile will die if its velocity drops too low.
*   **`damage`**: `0` - The projectile itself deals no direct damage; damage is solely from the explosion.
*   **`on_collision_die`**: `1` - The projectile dies upon colliding with anything.
*   **`lifetime`**: `1` - The projectile exists for a very short duration before expiring.

### Explosion Configuration (`config_explosion`)

This nested element defines the parameters of the explosion that occurs.

| Attribute                 | Value                                                                                              | Description