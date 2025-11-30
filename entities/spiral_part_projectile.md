---
title: Spiral Part Projectile
category: entities
---

# Spiral Part Projectile

This document describes the `spiral_part.xml` entity, which defines a projectile component used in Noita mods. It's designed to be a small, persistent projectile with a unique visual and particle effect.

## Key Components and Attributes

### Entity Definition

*   **`name`**: `$projectile_default` - Indicates this entity inherits default projectile properties.
*   **`tags`**: `spiral_part` - A custom tag for identifying this specific projectile type.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This section inherits core projectile behaviors.

*   **`VelocityComponent`**:
    *   **`gravity_y`**: `0` - The projectile is not affected by gravity.
    *   **`air_friction`**: `0` - No air resistance.

### Projectile Component (`ProjectileComponent`)

This defines the projectile's core mechanics.

*   **`_enabled`**: `1` - The component is active.
*   **`lob_min`**: `0.8` - Minimum lob angle.
*   **`lob_max`**: `1.0` - Maximum lob angle.
*   **`speed_min`**: `100` - Minimum projectile speed.
*   **`speed_max`**: `120` - Maximum projectile speed.
*   **`die_on_low_velocity`**: `0` - The projectile does not die when its velocity becomes low.
*   **`on_death_explode`**: `0` - The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode`**: `0` - The projectile does not explode when its lifetime ends.
*   **`explosion_dont_damage_shooter`**: `1` - If an explosion were to occur, it wouldn't damage the shooter.
*   **`damage`**: `0.17` - The base damage dealt by the projectile.
*   **`go_through_this_material`**: `crystal` - The projectile can pass through 'crystal' material without dying.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision with most surfaces.
*   **`lifetime`**: `9999` - A very long lifetime, making the projectile persistent.

### Sprite Component (`SpriteComponent`)

This defines the visual appearance of the projectile.

*   **`_enabled`**: `1` - The sprite is active.
*   **`alpha`**: `1` - The sprite is fully opaque.
*   **`image_file`**: `data/particles/star.xml` - Uses a star particle as its visual representation.
*   **`offset_x`**: `6` - Horizontal offset of the sprite.
*   **`offset_y`**: `6` - Vertical offset of the sprite.
*   **`additive`**: `1` - The sprite uses additive blending, making it appear brighter.
*   **`rect_animation`**: `spawn` - Uses the 'spawn' animation from the sprite sheet.
*   **`update_transform_rotation`**: `0` - The sprite's rotation does not update with the projectile's transform.

### Particle Emitter Components (`ParticleEmitterComponent`)

Two identical particle emitters are present, likely for a subtle visual effect.

*   **`emitted_material_name`**: `plasma_fading` - Emits particles of the 'plasma\_fading' material.
*   **`gravity.y`**: `0.0` - Emitted particles are not affected by gravity.
*   **`lifetime_min`**: `0.1` - Minimum lifetime of emitted particles.
*   **`lifetime_max`**: `1.5` - Maximum lifetime of emitted particles.
*   **`count_min`**: `1` - Minimum number of particles emitted per emission.
*   **`count_max`**: `1` - Maximum number of particles emitted per emission.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime progresses.
*   **`cosmetic_force_create`**: `0` - Particles are not forced to be cosmetic.
*   **`airflow_force`**: `0.3` - Applies a force related to airflow.
*   **`airflow_time`**: `0.01` - Duration of the airflow effect.
*   **`airflow_scale`**: `0.05` - Scale of the airflow effect.
*   **`emission_interval_min_frames`**: `0` - No delay between emissions.
*   **`emission_interval_max_frames`**: `0` - No delay between emissions.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.
*   **`is_emitting`**: `1` - The emitter is active.

### Variable Storage Component (`VariableStorageComponent`)

*   **`_tags`**: `theta` - A tag associated with this variable.
*   **`name`**: `theta` - The name of the variable.
*   **`value_float`**: `0` - The initial float value of the variable. This might be used for rotational calculations or other dynamic behaviors.

### Light Component (`LightComponent`)

Adds a light source to the projectile.

*   **`_enabled`**: `1` - The light is active.
*   **`radius`**: `90` - The radius of the light.
*   **`r`**: `30` - Red component of the light color.
*   **`g`**: `95` - Green component of the light color.
*   **`b`**: `160` - Blue component of the light color.