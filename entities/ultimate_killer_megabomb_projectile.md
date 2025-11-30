---
title: Ultimate Killer Megabomb Projectile
category: entities
---

# Ultimate Killer Megabomb Projectile

This document details the configuration for the "Ultimate Killer Megabomb" projectile in Noita, focusing on its core attributes and behaviors.

## Projectile Component

The `ProjectileComponent` defines the fundamental physics and interaction properties of the projectile.

### Key Attributes:

*   **`projectile_type`**: `MATERIAL_PARTICLE` - Indicates this projectile is a material particle.
*   **`lob_min` / `lob_max`**: `1.0` - The projectile has a fixed lob trajectory.
*   **`speed_min` / `speed_max`**: `123` / `135` - Defines the projectile's speed range.
*   **`friction`**: `3.0` - Controls how quickly the projectile loses momentum.
*   **`direction_random_rad`**: `0.0` - The projectile travels in a precise direction with no randomness.
*   **`on_death_emit_particle`**: `1` - A particle effect is spawned when the projectile dies.
*   **`on_death_emit_particle_type`**: `plant_material` - The type of particle emitted upon death.
*   **`on_death_particle_check_concrete`**: `1` - The particle emission checks for concrete surfaces.
*   **`explosion_dont_damage_shooter`**: `1` - The shooter is immune to damage from this projectile's explosion.
*   **`die_on_liquid_collision`**: `1` - The projectile is destroyed upon colliding with liquids.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon any collision.
*   **`lifetime`**: `360` - The projectile's lifespan in frames.
*   **`damage`**: `0` - This projectile deals no direct damage.
*   **`velocity_sets_scale`**: `1` - The projectile's velocity influences its scale.
*   **`lifetime_randomness`**: `7` - A small degree of randomness in its lifespan.
*   **`camera_shake_when_shot`**: `1.0` - Triggers a significant camera shake when fired.

## Sprite Component

The `SpriteComponent` handles the visual representation of the projectile.

### Key Attributes:

*   **`image_file`**: `data/projectiles_gfx/dirt.xml` - Specifies the graphical asset used for the projectile.

## Variable Storage Component

This component stores custom variables associated with the entity.

### Key Attributes:

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/ultimate_killer_megabomb.xml` - The value of the variable, pointing to the projectile's own XML file.