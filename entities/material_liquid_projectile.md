---
title: Material Liquid Projectile
category: entities
---

# Material Liquid Projectile

This document describes the configuration for a default material liquid projectile in Noita, primarily focusing on its behavior and visual representation.

## Projectile Component

The `ProjectileComponent` defines the core mechanics of the projectile.

### Key Attributes:

*   **`projectile_type`**: `MATERIAL_PARTICLE` - Indicates this projectile is a particle that carries material properties.
*   **`lob_min` / `lob_max`**: `1.0` - No lobbing behavior, travels in a straight line.
*   **`speed_min` / `speed_max`**: `123` / `135` - Defines the projectile's initial velocity range.
*   **`friction`**: `3.0` - Controls how quickly the projectile loses speed.
*   **`on_death_emit_particle`**: `1` - When the projectile dies, it emits another particle.
*   **`on_death_emit_particle_type`**: `_MATERIAL_SUCKER_` - The type of particle emitted upon death.
*   **`die_on_liquid_collision`**: `1` - The projectile will be destroyed upon colliding with any liquid.
*   **`on_collision_die`**: `1` - The projectile will be destroyed upon any collision.
*   **`lifetime`**: `360` - The maximum duration the projectile exists in seconds.
*   **`damage`**: `0` - This projectile does not deal direct damage.
*   **`camera_shake_when_shot`**: `1.0` - Triggers a camera shake effect when the projectile is fired.

## Sprite Component

The `SpriteComponent` handles the visual appearance of the projectile.

### Key Attributes:

*   **`image_file`**: `data/projectiles_gfx/dirt.xml` - Specifies the graphical asset used for the projectile. This suggests the default material liquid projectile uses a "dirt" graphic.