---
title: Enlightened Laser Fireball Projectile
category: entities
---

# Enlightened Laser Fireball Projectile

This document details the configuration of the "enlightened_laser_fireball.xml" entity, which defines a player projectile in Noita.

## Core Components

### Entity Definition

The projectile is defined as an `Entity` with the tag `projectile_player`.

### Base Projectile Configuration

Inherits from `data/entities/base_projectile.xml`.

*   **`VelocityComponent`**:
    *   `gravity_y`: 50 (Applies downward gravitational pull)
    *   `air_friction`: 0 (No air resistance)
    *   `mass`: 0.3 (Light mass)

### Projectile Component (`ProjectileComponent`)

This is the primary component defining the projectile's behavior.

*   **`_enabled`**: 1 (Component is active)
*   **`lob_min` / `lob_max`**: 0.8 / 1.0 (Controls the arc of the projectile)
*   **`speed_min` / `speed_max`**: 300 / 400 (Initial velocity range)
*   **`die_on_low_velocity`**: 1 (Projectile is destroyed if its speed drops too low)
*   **`on_death_explode`**: 1 (Explodes upon death)
*   **`on_lifetime_out_explode`**: 1 (Explodes when its lifetime expires)
*   **`explosion_dont_damage_shooter`**: 1 (The explosion will not harm the entity that fired it)
*   **`damage`**: 0 (Base damage of the projectile itself, before type-specific damage)
*   **`on_collision_die`**: 1 (Projectile is destroyed on collision)
*   **`die_on_liquid_collision`**: 1 (Projectile is destroyed when colliding with liquids)
*   **`lifetime`**: 200 (Duration in frames before expiring)
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml` (Visual effect at firing point)
*   **`shoot_light_flash_r` / `g` / `b` / `radius`**: 255 / 210 / 40 / 120 (Color and radius of the light flash when fired)
*   **`knockback_force`**: 3.0 (Force applied to entities it hits)
*   **`physics_impulse_coeff`**: 9000 (Coefficient for physics impulse on impact)

#### `damage_by_type`

*   **`fire`**: 2.25 (Additional fire damage applied)

#### `config_explosion`

Defines the properties of the explosion when the projectile dies.

*   **`never_cache`**: 1 (Ensures the explosion is always generated fresh)
*   **`camera_shake`**: 20.5 (Intensity of camera shake on explosion)
*   **`explosion_radius`**: 45 (Radius of the explosion effect)
*   **`explosion_sprite`**: `data/particles/explosion_040_poof.xml` (Visual sprite for the explosion)
*   **`create_cell_probability`**: 100 (100% chance to create material cells)
*   **`create_cell_material`**: `fire` (The material created by the explosion)
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main.xml,data/entities/misc/loose_ground.xml` (Entities spawned by the explosion)
*   **`ray_energy`**: 7500000 (Energy value for raycasting effects from the explosion)
*   **`hole_enabled`**: 1 (Creates a hole in terrain)
*   **`particle_effect`**: 1 (Enables particle effects for the explosion)
*   **`damage_mortals`**: 1 (Explosion damages living entities)
*   **`physics_explosion_power.min` / `max`**: 2 / 4 (Minimum and maximum physics force of the explosion)
*   **`physics_throw_enabled`**: 1 (Entities can be thrown by the explosion)
*   **`shake_vegetation`**: 1 (Causes vegetation to shake)
*   **`sparks_enabled`**: 1 (Sparks are generated)
*   **`sparks_count_min` / `max`**: 50 / 100 (Number of sparks)
*   **`stains_enabled`**: 1 (Creates stains on surfaces)
*   **`stains_image`**: `data/temp/explosion_stain.png` (Image used for stains)

### Sprite Component (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   **`image_file`**: `data/projectiles_gfx/meteor.xml` (The sprite asset used)
*   **`emissive`**: 1 (Sprite emits light)
*   **`additive`**: 1 (Sprite uses additive blending)
*   **`z_index`**: -0.5 (Rendering layer)

### Particle Emitters

Multiple `ParticleEmitterComponent` instances are used to create visual effects.

*   **Smoke Emitter**:
    *   `emitted_material_name`: `smoke`
    *   `count_min`/`max`: 5 / 5
    *   `lifetime_min`/`max`: 0.1 / 0.3
    *   `is_emitting`: 1
*   **Fire Emitter 1**:
    *   `emitted_material_name`: `fire`
    *   `count_min`/`max`: 1 / 1
    *   `lifetime_min`/`max`: 0.1 / 0.3
    *   `is_emitting`: 1
*   **Fire Emitter 2 (Delayed)**:
    *   `emitted_material_name`: `fire`
    *   `custom_style`: `FIRE`
    *   `count_min`/`max`: 6 / 6
    *   `lifetime_min`/`max`: 1.1 / 2.8
    *   `delay_frames`: 2
    *   `is_emitting`: 0 (Starts emitting after delay)
*   **Spark Emitter**:
    *   `emitted_material_name`: `spark`
    *   `count_min`/`max`: 40 / 100
    *   `lifetime_min`/`max`: 0.2 / 0.4
    *   `airflow_force`: 2.5
    *   `emit_cosmetic_particles`: 1
    *   `create_real_particles`: 0
    *   `is_emitting`: 1
*   **Fire Particle Emitter (Cosmetic)**:
    *   `emitted_material_name`: `fire`
    *   `count_min`/`max`: 80 / 120
    *   `lifetime_min`/`max`: 0.1 / 0.2
    *   `airflow_force`: 8.5
    *   `emit_cosmetic_particles`: 1
    *   `create_real_particles`: 0
    *   `is_emitting`: 0
*   **Sprite Particle Emitter**:
    *   `sprite_file`: `data/particles/fire_large.xml`
    *   `count_min`/`max`: 3 / 5
    *   `randomize_position`: -7 to 7 (x and y)
    *   `is_emitting`: 1

### Light Component (`LightComponent`)

*   **`radius`**: 150 (The radius of the light emitted by the projectile)

### Variable Storage Component (`VariableStorageComponent`)

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/enlightened_laser_fireball.xml` (Stores the path to this entity file)