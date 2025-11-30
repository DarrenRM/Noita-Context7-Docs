---
title: Enlightened Laser Dark Wand Projectile
category: entities
---

# Enlightened Laser Dark Wand Projectile

This document details the configuration for the "Enlightened Laser Dark Wand" projectile in Noita, focusing on its key attributes for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior of the projectile.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `speed_min`               | `1`     | Minimum projectile speed.                                                   |
| `speed_max`               | `1`     | Maximum projectile speed.                                                   |
| `friction`                | `0.0`   | How much the projectile slows down over time.                               |
| `direction_random_rad`    | `0.05`  | Random deviation in projectile direction (in radians).                        |
| `lifetime`                | `52`    | Duration the projectile exists before expiring (in frames).                 |
| `damage`                  | `5`     | Base damage dealt by the projectile.                                        |
| `hit_particle_force_multiplier` | `5.5` | Multiplier for the force applied to particles upon collision.               |
| `camera_shake_when_shot`  | `3.0`   | Intensity of camera shake when this projectile is fired.                    |
| `shoot_light_flash_radius`| `80`    | Radius of the light flash effect when the projectile is shot.               |
| `knockback_force`         | `2.5`   | Force applied to entities that are hit by the projectile.                   |
| `collide_with_world`      | `0`     | Whether the projectile can collide with the game world geometry.            |
| `penetrate_entities`      | `0`     | Whether the projectile can pass through other entities.                     |

## Scripting and Logic

The `LuaComponent` links custom scripting to the projectile's behavior.

```xml
<LuaComponent
    script_source_file="data/scripts/projectiles/enlightened_laser_dark.lua"
    execute_every_n_frame="50"
    remove_after_executed="1"
    >
</LuaComponent>
```

*   **`script_source_file`**: Specifies the Lua script responsible for advanced projectile logic.
*   **`execute_every_n_frame`**: The script will execute every 50 frames.
*   **`remove_after_executed`**: The script will be removed after its first execution.

## Visual Effects (Particle Emitters)

This projectile utilizes several `ParticleEmitterComponent`s to create visual effects.

### Image Emitter

This emitter generates cosmetic particles.

```xml
<ParticleEmitterComponent
    emitted_material_name="spark_purple_bright"
    lifetime_min="0.5"
    lifetime_max="2"
    count_min="1"
    count_max="1"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    airflow_force="0.051"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    direction_random_deg="90"
    emit_cosmetic_particles="1"
    image_animation_file="data/particles/image_emitters/wand_64.png"
    image_animation_speed="10"
    image_animation_emission_probability="0.8"
    image_animation_loop="0"
    image_animation_use_entity_rotation="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `spark_purple_bright`
*   **`image_animation_file`**: `data/particles/image_emitters/wand_64.png` - Uses a specific animation for particle appearance.

### Launch Blast A

A burst of particles upon firing.

```xml
<ParticleEmitterComponent
    emitted_material_name="spark_purple_bright"
    delay_frames="45"
    offset.x="27"
    x_vel_min="-20"
    x_vel_max="800"
    y_vel_min="-30"
    y_vel_max="30"
    velocity_always_away_from_center="1"
    area_circle_radius.min="10"
    area_circle_radius.max="10"
    friction="4"
    count_min="30"
    count_max="50"
    lifetime_min="0.1"
    lifetime_max="0.4"
    emitter_lifetime_frames="3"
    emit_real_particles="0"
    render_on_grid="1"
    emit_cosmetic_particles="1"
    fade_based_on_lifetime="0"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`delay_frames`**: `45` - The effect starts 45 frames after the projectile is created.
*   **`offset.x`**: `27` - Positioned slightly ahead of the projectile's origin.
*   **`emit_real_particles`**: `0` - These are cosmetic particles, not affecting gameplay directly.

### Launch Blast Circle

A circular burst of particles.

```xml
<ParticleEmitterComponent
    emitted_material_name="spark_purple_bright"
    delay_frames="44"
    offset.x="27"
    x_vel_min="-0"
    x_vel_max="40"
    y_vel_min="-5"
    y_vel_max="5"
    velocity_always_away_from_center="1"
    area_circle_radius.min="9"
    area_circle_radius.max="9"
    friction="0.5"
    count_min="30"
    count_max="60"
    lifetime_min="0.2"
    lifetime_max="1.0"
    emitter_lifetime_frames="2"
    emit_real_particles="0"
    render_on_grid="1"
    emit_cosmetic_particles="1"
    fade_based_on_lifetime="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`delay_frames`**: `44` - Similar timing to "Launch Blast A".
*   **`area_circle_radius`**: `9` - Defines the circular area of emission.

## Lighting

A `LightComponent` adds a light source when the projectile is active.

```xml
<LightComponent
    radius="100" >
</LightComponent>
```

*   **`radius`**: `100` - The radius of the light emitted.

## Audio

The `AudioComponent` links sound effects to the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="projectiles/enlightened_laser">
</AudioComponent>
```

*   **`event_root`**: `projectiles/enlightened_laser` - Specifies the sound event group.

## Variable Storage

The `VariableStorageComponent` stores a reference to the projectile's own XML file.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/enlightened_laser_dark_wand.xml"
    >
</VariableStorageComponent>
```