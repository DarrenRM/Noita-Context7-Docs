---
title: TNT Projectile
category: entities
---

# TNT Projectile

This document details the configuration for the TNT projectile entity in Noita, designed for AI-assisted modding.

## Core Components

### Base Projectile Physics

This section defines the fundamental physical properties and behavior of the projectile.

*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/projectiles_gfx/tnt.png` - Specifies the visual sprite for the TNT projectile.
    *   `material`: `fuse_tnt` - Assigns a material property, likely influencing interactions and physics.
*   **`PhysicsThrowableComponent`**:
    *   `throw_force_coeff`: `2.5` - A coefficient that modifies the force applied when the projectile is thrown.
*   **`ProjectileComponent`**:
    *   `speed_min`, `speed_max`: `800` - Sets the projectile's speed.
    *   `damage`: `0` - The direct damage dealt by the projectile itself (before explosion).
    *   `lifetime`: `50` - The duration in frames before the projectile is destroyed if it doesn't hit anything.

### Explosion Configuration

This nested configuration within `ProjectileComponent` defines the properties of the explosion that occurs upon impact or destruction.

*   **`config_explosion`**:
    *   `damage`: `2.5` - The damage dealt by the explosion.
    *   `explosion_radius`: `28` - The radius of the explosion's effect.
    *   `explosion_sprite`: `data/particles/explosion_032.xml` - The visual effect used for the explosion.
    *   `load_this_entity`: `data/entities/particles/particle_explosion/main_gunpowder_medium.xml` - The entity to load for the explosion's particle effects.
    *   `audio_event_name`: `explosions/tnt` - The audio event triggered by the explosion.
    *   `max_durability_to_destroy`: `11` - The amount of durability an object needs to have to be destroyed by this explosion.

## Visual Effects (Particle Emitters)

The following `ParticleEmitterComponent` entries define the visual effects associated with the TNT projectile.

### Smoke Emission

*   **`emitted_material_name`**: `smoke`
*   **`offset.x`, `offset.y`**: `2`, `-3` - Position offset for the emitter.
*   **`x_pos_offset_min/max`, `y_pos_offset_min/max`**: Defines the spread of emitted particles.
*   **`x_vel_min/max`, `y_vel_min/max`**: Sets the initial velocity range for smoke particles.
*   **`count_min/max`**: `0`, `4` - Number of particles emitted per interval.
*   **`lifetime_min/max`**: `0.1`, `0.3` - Duration of smoke particles.
*   **`create_real_particles`**: `1` - Indicates these are actual game particles.
*   **`emit_cosmetic_particles`**: `0` - These are not purely cosmetic.
*   **`emission_interval_min/max_frames`**: `1`, `1` - Emits particles every frame.
*   **`is_emitting`**: `1` - The emitter is active.

### Spark Emission (Cosmetic)

*   **`emitted_material_name`**: `spark`
*   **`offset.x`, `offset.y`**: `2`, `-3`
*   **`fade_based_on_lifetime`**: `1` - Particles fade as their lifetime ends.
*   **`x_pos_offset_min/max`, `y_pos_offset_min/max`**: Defines particle spread.
*   **`x_vel_min/max`, `y_vel_min/max`**: Sets initial velocity for sparks.
*   **`count_min/max`**: `1`, `2` - Number of sparks emitted.
*   **`lifetime_min/max`**: `0.1`, `0.3` - Duration of spark particles.
*   **`create_real_particles`**: `0` - These are cosmetic particles.
*   **`emit_cosmetic_particles`**: `1` - Explicitly cosmetic.
*   **`emission_interval_min/max_frames`**: `1`, `1`
*   **`is_emitting`**: `1`

### Sparse Spark Trail Emission

*   **`emitted_material_name`**: `spark`
*   **`offset.x`, `offset.y`**: `2`, `-3`
*   **`x_vel_min/max`**: `10`, `20` - Sparks are emitted with a forward velocity.
*   **`y_vel_min/max`**: `0`, `0` - No vertical velocity.
*   **`gravity.y`**: `0.0` - No gravity applied to these sparks.
*   **`count_min/max`**: `1`, `1` - Emits one spark at a time.
*   **`lifetime_min/max`**: `1.4`, `1.5` - Longer lifetime for trail sparks.
*   **`is_trail`**: `0` - Not a continuous trail, but individual sparks.
*   **`trail_gap`**: `8.0` - (Note: `is_trail` is 0, so this might be less relevant or interpreted differently).
*   **`render_on_grid`**: `1` - Renders even on the grid.
*   **`fade_based_on_lifetime`**: `1`
*   **`airflow_force`, `airflow_time`, `airflow_scale`**: `0.5`, `0.5`, `0.05` - Parameters for airflow interaction.
*   **`emission_interval_min/max_frames`**: `10`, `30` - Emits sparks less frequently.
*   **`emit_cosmetic_particles`**: `1`
*   **`create_real_particles`**: `0`
*   **`is_emitting`**: `1`

## Audio Components

### Main Audio Component

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing projectile sounds.
*   **`event_root`**: `player_projectiles/bomb` - The root event for player projectile sounds, specifically for bombs.

### Fuse Burn Loop Component

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_name`**: `projectiles/fuse_burn_fast` - The specific sound event for the fast fuse burn.
*   **`auto_play`**: `1` - The sound starts playing automatically when the entity is active.

## Variable Storage

*   **`VariableStorageComponent`**:
    *   `name`: `projectile_file`
    *   `value_string`: `data/entities/projectiles/deck/tnt.xml` - Stores the path to this entity's XML file, useful for referencing.