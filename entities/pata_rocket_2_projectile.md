---
title: Pata Rocket 2 Projectile
category: entities
---

# Pata Rocket 2 Projectile

This document details the configuration for the "Pata Rocket 2" projectile entity in Noita, focusing on its core attributes and behaviors relevant to AI-assisted modding.

## Core Entity Properties

*   **`name`**: `$projectile_default` (Inherited, but this specific entity is named "pata_rocket_2" via `VariableStorageComponent`)
*   **`tags`**: `projectile_player`, `rocket`

## Key Components and Attributes

### Base Projectile Configuration (`BaseComponent`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y`: `50` (Applies downward gravitational pull)
    *   `air_friction`: `-5.0` (Resistance to movement in air)
    *   `mass`: `0.05` (Lightweight projectile)

### Projectile Behavior (`ProjectileComponent`)

This is the primary component defining the projectile's actions and effects.

*   **`_enabled`**: `1` (Component is active)
*   **`lob_min` / `lob_max`**: `0.8` / `1.0` (Controls the arc of the projectile, with minimal randomness)
*   **`speed_min` / `speed_max`**: `70` / `100` (Initial velocity range)
*   **`direction_random_rad`**: `0.0` (No initial directional randomness)
*   **`on_death_explode`**: `1` (Explodes upon death)
*   **`on_lifetime_out_explode`**: `1` (Explodes when its lifetime expires)
*   **`on_collision_die`**: `1` (Dies and explodes upon collision)
*   **`lifetime`**: `40` (Base duration before expiring)
*   **`lifetime_randomness`**: `20` (Adds variability to the projectile's lifespan)
*   **`damage`**: `5` (Base damage dealt by the projectile itself)
*   **`velocity_sets_scale`**: `1` (Velocity influences scaling, likely visual)
*   **`knockback_force`**: `4.0` (Force applied to entities upon impact)
*   **`physics_impulse_coeff`**: `5000` (Coefficient for physics impulse, affecting knockback strength)
*   **`camera_shake_when_shot`**: `15.0` (Amount of camera shake when fired)
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher.xml` (Visual effect at the muzzle)
*   **`shoot_light_flash_r` / `g` / `b` / `radius`**: `215` / `40` / `255` / `90` (Color and radius of light emitted when shot)

#### Explosion Configuration (`config_explosion`)

Defines the properties of the explosion when the projectile dies.

*   **`never_cache`**: `1` (Ensures the explosion is always generated fresh)
*   **`camera_shake`**: `90` (Significant camera shake upon explosion)
*   **`explosion_radius`**: `30` (Area of effect for the explosion)
*   **`explosion_sprite`**: `data/particles/explosion_032_pink.xml` (Visual sprite for the explosion)
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_swirly_red_giga.xml` (Entity spawned by the explosion)
*   **`hole_enabled`**: `1` (Creates holes in terrain)
*   **`ray_energy`**: `6200000` (Energy for raycasting effects from the explosion)
*   **`damage`**: `5.2` (Damage dealt by the explosion)
*   **`damage_mortals`**: `1` (Explosion damages living entities)
*   **`physics_explosion_power.min` / `max`**: `1.0` / `1.4` (Force of the physics-based explosion)
*   **`physics_throw_enabled`**: `1` (Entities are thrown by the explosion)
*   **`sparks_enabled`**: `1` (Generates sparks)
*   **`spark_material`**: `spark_red` (Type of sparks generated)
*   **`sparks_count_min` / `max`**: `60` / `90` (Number of sparks)
*   **`stains_enabled`**: `1` (Creates stains on surfaces)
*   **`stains_radius`**: `20` (Radius of the stains)
*   **`audio_event_name`**: `explosions/magic_rocket_big` (Sound effect for the explosion)

### Visuals (`SpriteComponent`)

*   **`_enabled`**: `0` (This sprite is disabled, likely meaning the visual is handled by particle emitters or the loaded explosion entity)
*   **`image_file`**: `data/projectiles_gfx/fireball_small.xml` (Placeholder or unused sprite)

### Lighting (`LightComponent`)

*   **`_enabled`**: `1` (Emits light)
*   **`r` / `g` / `b`**: `100` / `10` / `255` (Purple light color)
*   **`radius`**: `150` (Radius of the light)

### Particle Emitters (`ParticleEmitterComponent`)

Multiple emitters contribute to the projectile's visual trail and explosion effects.

*   **Emitter 1 (Smoke Trail)**:
    *   `emitted_material_name`: `smoke`
    *   `count_min`/`max`: `5`
    *   `lifetime_min`/`max`: `0.1` / `0.3`
    *   `create_real_particles`: `1`
    *   `is_emitting`: `1`

*   **Emitters 2-5 (Red Sparks - Various Gravity/Lifetime)**:
    *   `emitted_material_name`: `spark_red`
    *   These emitters create trails of red sparks with varying gravity (`gravity.y`), lifetimes, and airflow effects to simulate a dynamic trail. Some are cosmetic (`emit_cosmetic_particles="1"`), others real.

*   **Emitter 6 (Sparse Trail)**:
    *   `emitted_material_name`: `spark_red`
    *   `count_min`/`max`: `1`
    *   `lifetime_min`/`max`: `1.4` / `2.5`
    *   `emission_interval_min_frames`/`max_frames`: `8` / `12` (Sparse emission)
    *   `is_trail`: `0` (Not a continuous trail, but individual sparks)

*   **Emitter 7 (Explosion Sparks)**:
    *   `emitted_material_name`: `spark_red`
    *   `count_min`/`max`: `10` / `20`
    *   `lifetime_min`/`max`: `1.6` / `3.9`
    *   `gravity.y`: `20` (Downward pull on explosion sparks)
    *   `is_emitting`: `1`

### Audio (`AudioComponent`)

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/bullet_rocket` (Plays a rocket projectile sound when fired)

### Variable Storage (`VariableStorageComponent`)

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/pata_rocket_2.xml` (Self-referential, useful for scripts)

### Scripting (`LuaComponent`)

*   **`script_source_file`**: `data/scripts/projectiles/pata_rocket_2.lua` (External Lua script for custom logic)
*   **`execute_every_n_frame`**: `1` (Script logic runs every frame)