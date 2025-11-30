---
title: Enlightened Laser Fire Wand Projectile
category: entities
---

# Enlightened Laser Fire Wand Projectile

This document details the configuration for the "enlightened_laser_fire_wand.xml" projectile entity in Noita, designed for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior and impact of the projectile.

### Key Attributes:

*   **`speed_min` / `speed_max`**: `1` - The projectile travels at a constant speed.
*   **`friction`**: `0.0` - No friction, maintaining its speed.
*   **`direction_random_rad`**: `0.05` - Slight randomness in projectile direction.
*   **`lifetime`**: `62` - The projectile exists for 62 frames before expiring.
*   **`damage`**: `5` - The amount of damage dealt on impact.
*   **`hit_particle_force_multiplier`**: `5.5` - Controls the force of particles spawned on impact.
*   **`camera_shake_when_shot`**: `3.0` - Triggers camera shake when the projectile is fired.
*   **`shoot_light_flash_radius`**: `80` - The radius of the light flash when the projectile is shot.
*   **`knockback_force`**: `2.5` - The force applied to knock back entities on impact.
*   **`collide_with_world`**: `0` - The projectile does not collide with the environment.
*   **`penetrate_entities`**: `0` - The projectile does not penetrate other entities.

## Scripting and Behavior

The `LuaComponent` links the projectile to custom scripting for advanced logic.

### Key Attributes:

*   **`script_source_file`**: `data/scripts/projectiles/enlightened_laser_fire.lua` - Specifies the Lua script that governs the projectile's behavior.
*   **`execute_every_n_frame`**: `60` - The script executes every 60 frames.
*   **`remove_after_executed`**: `1` - The projectile is removed from the game after the script has executed once.

## Visual Effects (Particle Emitters)

Multiple `ParticleEmitterComponent` instances are used to create visual effects associated with the projectile.

### 1. Image Emitter (Trail/Spark)

*   **`emitted_material_name`**: `spark` - The material used for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `2` - Duration of individual particles.
*   **`count_min` / `count_max`**: `1` / `1` - Number of particles emitted per cycle.
*   **`airflow_force`**: `0.051` - Controls airflow influence on particles.
*   **`image_animation_file`**: `data/particles/image_emitters/wand_64.png` - The sprite sheet for animated particles.
*   **`image_animation_speed`**: `6` - Speed of the particle animation.
*   **`is_emitting`**: `1` - The emitter is active.

### 2. Launch Blast A (Muzzle Flash/Burst)

*   **`emitted_material_name`**: `spark`
*   **`delay_frames`**: `55` - The emitter activates 55 frames after the projectile is created.
*   **`offset.x`**: `27` - Offset from the projectile's origin.
*   **`x_vel_min` / `x_vel_max`**: `-20` / `800` - Velocity range for emitted particles.
*   **`y_vel_min` / `y_vel_max`**: `-30` / `30` - Velocity range for emitted particles.
*   **`velocity_always_away_from_center`**: `1` - Particles are always emitted away from the center.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `10` / `10` - The emission area.
*   **`count_min` / `count_max`**: `30` / `50` - Number of particles emitted.
*   **`lifetime_min` / `lifetime_max`**: `0.1` / `0.4` - Duration of these particles.
*   **`emitter_lifetime_frames`**: `3` - How long the emitter itself is active.
*   **`emit_real_particles`**: `0` - Emits cosmetic particles.

### 3. Launch Blast Circle (Ring Effect)

*   **`emitted_material_name`**: `spark`
*   **`delay_frames`**: `54` - Activates just before "Launch Blast A".
*   **`offset.x`**: `27` - Offset from the projectile's origin.
*   **`x_vel_min` / `x_vel_max`**: `0` / `40` - Velocity range.
*   **`y_vel_min` / `y_vel_max`**: `-5` / `5` - Velocity range.
*   **`velocity_always_away_from_center`**: `1`
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `9` / `9` - Emission area.
*   **`count_min` / `count_max`**: `30` / `60` - Number of particles emitted.
*   **`lifetime_min` / `lifetime_max`**: `0.2` / `1.0` - Duration of these particles.
*   **`emitter_lifetime_frames`**: `2` - How long the emitter itself is active.
*   **`emit_real_particles`**: `0` - Emits cosmetic particles.

## Lighting

The `LightComponent` adds a light source to the projectile.

### Key Attributes:

*   **`radius`**: `100` - The radius of the light emitted by the projectile.

## Audio

The `AudioComponent` defines the sound effects associated with the projectile.

### Key Attributes:

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `projectiles/enlightened_laser` - The root event name for projectile sounds.

## Variable Storage

The `VariableStorageComponent` stores custom variables for use within the game or scripts.

### Key Attributes:

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/enlightened_laser_fire_wand.xml` - Stores the path to this projectile's entity file.