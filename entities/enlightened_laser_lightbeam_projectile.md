---
title: Enlightened Laser Lightbeam Projectile
category: entities
---

---

# Enlightened Laser Lightbeam Projectile

This document details the configuration for the "enlightened_laser_lightbeam.xml" projectile entity in Noita, designed for AI-assisted modding.

## Core Components

The projectile is built upon several core Noita entity components, defining its behavior, appearance, and effects.

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is unaffected by gravity.
    *   `mass="0.09"`: Defines the projectile's mass.
    *   `air_friction="-1"`: Indicates no air friction, allowing for consistent velocity.

### Projectile Component (`<ProjectileComponent>`)

This is the primary component defining the projectile's unique characteristics.

*   **`_enabled="1"`**: Ensures the component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the projectile's lobbing behavior, with minimal to no lob.
*   **`speed_min="800"`, `speed_max="900"`**: Sets the projectile's initial velocity range.
*   **`friction="1"`**: Applies friction to the projectile.
*   **`direction_random_rad="0.03"`**: Introduces a small amount of randomness to the projectile's direction.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision.
*   **`lifetime="90"`**: The base duration of the projectile in frames.
*   **`lifetime_randomness="7"`**: Adds variability to the projectile's lifetime.
*   **`damage="0.45"`**: The base damage dealt by the projectile.
*   **`knockback_force="2.8"`**: The force applied to knock back entities upon impact.
*   **`camera_shake_when_shot="0.4"`**: The intensity of camera shake when the projectile is fired.
*   **`shoot_light_flash_r="250"`, `shoot_light_flash_g="250"`, `shoot_light_flash_b="250"`**: Defines the RGB color of the muzzle flash.
*   **`shoot_light_flash_radius="100"`**: The radius of the muzzle flash light.
*   **`physics_impulse_coeff="4000"`**: Coefficient for physics impulse applied on impact.

#### Explosion Configuration (`<config_explosion>`)

Defines the properties of the explosion when the projectile dies.

*   **`damage="0.38"`**: Damage dealt by the explosion.
*   **`camera_shake="20.0"`**: Intensity of camera shake from the explosion.
*   **`explosion_radius="20"`**: The radius of the explosion.
*   **`ray_energy="2050000"`**: The energy of the explosion's rays.
*   **`max_durability_to_destroy="11"`**: Maximum durability of objects that can be destroyed by the explosion.
*   **`physics_explosion_power.min="0.15"`, `physics_explosion_power.max="0.35"`**: Range for the physics force of the explosion.
*   **`sparks_enabled="1"`**: Enables sparks from the explosion.
*   **`sparks_count_min="60"`, `sparks_count_max="50"`**: Defines the range for the number of sparks. (Note: `min` is greater than `max`, which might be a typo or intended behavior).
*   **`spark_material="spark_white"`**: The material used for the sparks.
*   **`stains_enabled="1"`**: Enables stains on surfaces from the explosion.
*   **`stains_radius="1"`**: The radius of the stains.

### Light Component (`<LightComponent>`)

Adds a light source to the projectile.

*   **`_enabled="1"`**: Ensures the component is active.
*   **`radius="150"`**: The radius of the light emitted by the projectile.
*   **`r="180"`, `g="180"`, `b="180"`**: The RGB color of the light.

### Particle Emitter Components (`<ParticleEmitterComponent>`)

Two emitters are used to create visual effects.

*   **Emitter 1 (General Particles):**
    *   `emitted_material_name="spark_white"`: The material of the emitted particles.
    *   `count_min="1"`, `count_max="4"`: Number of particles emitted per interval.
    *   `lifetime_min="0.1"`, `lifetime_max="0.3"`: Duration of emitted particles.
    *   `emission_interval_min_frames="4"`, `emission_interval_max_frames="8"`: Frame interval between particle emissions.
    *   `emit_cosmetic_particles="1"`: Emits cosmetic particles.

*   **Emitter 2 (Trail Particles):**
    *   `emitted_material_name="spark_white"`: The material of the emitted particles.
    *   `lifetime_min="0.1"`, `lifetime_max="0.3"`: Duration of emitted particles.
    *   `is_trail="1"`: Marks this emitter as creating a trail.
    *   `trail_gap="1.5"`: The gap between trail particles.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="2"`: Frame interval for trail particle emission.
    *   `emit_cosmetic_particles="1"`: Emits cosmetic particles.

### Variable Storage Component (`<VariableStorageComponent>`)

Stores a variable related to the projectile.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/enlightened_laser_lightbeam.xml"`**: The value, referencing its own file path.