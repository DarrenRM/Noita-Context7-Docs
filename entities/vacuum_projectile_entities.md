---
title: Vacuum Projectile Entities
category: entities
---

# Vacuum Projectile Entities

This document details the configuration for the "Vacuum" projectile entity in Noita, focusing on its particle emission, projectile properties, and associated Lua scripting.

## Entity Definition

The core entity definition for the vacuum projectile.

```xml
<Entity 
  name="$projectile_default" 
>
  <!-- ... components ... -->
</Entity>
```

## Particle Emitter Components

These components define the visual effects of the vacuum projectile, primarily through the emission of "spark_blue" particles.

### ParticleEmitterComponent (Inner)

This emitter is responsible for the initial burst of particles.

*   **`emitted_material_name`**: `spark_blue` - Specifies the material of the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - Duration each particle exists.
*   **`count_min` / `count_max`**: `2` / `4` - Number of particles emitted per burst.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime ends.
*   **`area_circle_radius.max`**: `64` - The maximum radius of the emission area.
*   **`airflow_force`**: `1.7` - Strength of airflow affecting particles.
*   **`airflow_time`**: `0.11` - Duration airflow affects particles.
*   **`airflow_scale`**: `0.05` - Scale of the airflow effect.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted continuously.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.
*   **`attractor_force`**: `4` - Force attracting particles.
*   **`draw_as_long`**: `1` - Particles are drawn as elongated.
*   **`is_emitting`**: `1` - The emitter is active.

### ParticleEmitterComponent (Outer)

This emitter contributes to the sustained visual effect of the vacuum.

*   **`emitted_material_name`**: `spark_blue` - Specifies the material of the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `2.5` - Duration each particle exists.
*   **`count_min` / `count_max`**: `4` / `4` - Number of particles emitted per burst.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime ends.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `64` / `64` - The emission area is a circle with a radius of 64.
*   **`airflow_force`**: `0.8` - Strength of airflow affecting particles.
*   **`airflow_time`**: `0.11` - Duration airflow affects particles.
*   **`airflow_scale`**: `0.05` - Scale of the airflow effect.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted continuously.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.
*   **`attractor_force`**: `8` - Force attracting particles.
*   **`draw_as_long`**: `1` - Particles are drawn as elongated.
*   **`is_emitting`**: `1` - The emitter is active.

## Base Field Component

This section inherits properties from `base_field.xml`, providing fundamental projectile behavior.

### SpriteComponent

*   **`_enabled`**: `0` - This sprite component is disabled.

### SpriteParticleEmitterComponent

This component adds a shimmering visual effect.

*   **`sprite_file`**: `data/particles/shine_03.xml` - The sprite file used for the shine effect.
*   **`_enabled`**: `0` - This sprite particle emitter is disabled.
*   **`lifetime`**: `2` - Duration of the shine effect.
*   **`color.r` / `color.g` / `color.b` / `color.a`**: `1` / `1` / `1` / `1` - Initial color of the shine (white).
*   **`color_change.r` / `color_change.g` / `color_change.b` / `color_change.a`**: `0` / `0` / `0` / `-1` - Color changes over time (alpha decreases).
*   **`randomize_rotation.min` / `randomize_rotation.max`**: `-3.1415` / `3.1415` - Random initial rotation.
*   **`randomize_angular_velocity.min` / `randomize_angular_velocity.max`**: `-15` / `15` - Random angular velocity.

### ProjectileComponent

Defines the core projectile properties.

*   **`damage_game_effect_entities`**: `""` - No specific game effect entities are applied on damage.
*   **`friendly_fire`**: `0` - Projectile does not cause friendly fire.
*   **`lifetime`**: `20` - The projectile exists for 20 seconds.
*   **`config_explosion`**:
    *   **`explosion_sprite`**: `data/particles/blast_out_polymorph.xml` - The sprite used for the explosion effect.

### AudioLoopComponent

Handles the sound effect for the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound event.
*   **`event_name`**: `player_projectiles/field_transmutation/loop` - The name of the sound event to play.
*   **`auto_play`**: `1` - The sound starts automatically.

## Lua Component

This component links the entity to a Lua script for custom behavior.

*   **`script_source_file`**: `data/scripts/projectiles/vacuum_entities.lua` - The path to the Lua script.
*   **`execute_every_n_frame`**: `8` - The script executes every 8 frames.
*   **`remove_after_executed`**: `1` - The Lua component is removed after its first execution.