---
title: Material Debug Projectile
category: entities
---

# Material Debug Projectile

This document describes the `material_debug.xml` entity, which defines a projectile used for debugging material interactions in Noita.

## Entity Definition

The core entity is named `$projectile_default` and is tagged as `projectile_player`. It inherits functionality from `data/entities/base_projectile.xml`.

## ProjectileComponent

This component governs the behavior and properties of the projectile.

### Key Attributes:

*   **`projectile_type`**: `MATERIAL_PARTICLE` - Indicates this projectile is related to material particle effects.
*   **`lob_min` / `lob_max`**: `1.0` - No lobbing effect, projectile travels in a straight line.
*   **`speed_min` / `speed_max`**: `123` / `135` - Defines the projectile's initial speed range.
*   **`friction`**: `3.0` - Controls how quickly the projectile loses speed.
*   **`on_death_emit_particle`**: `1` - When the projectile dies, it emits a particle.
*   **`on_death_emit_particle_count`**: `1` - Emits a single particle upon death.
*   **`on_death_emit_particle_type`**: `_DEBUG_` - Specifies the type of particle to emit (likely a debug particle).
*   **`on_death_particle_check_concrete`**: `1` - The emitted particle will check for concrete surfaces.
*   **`die_on_liquid_collision`**: `1` - The projectile is destroyed upon colliding with liquids.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon any collision.
*   **`lifetime`**: `360` - The projectile's lifespan in frames.
*   **`damage`**: `0` - This projectile deals no damage.
*   **`camera_shake_when_shot`**: `1.0` - Triggers camera shake when the projectile is fired.

## SpriteComponent

This component defines the visual representation of the projectile.

### Key Attributes:

*   **`image_file`**: `data/projectiles_gfx/dirt.xml` - Specifies the graphical asset used for the projectile.