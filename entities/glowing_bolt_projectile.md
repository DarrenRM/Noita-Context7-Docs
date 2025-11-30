---
title: Glowing Bolt Projectile
category: entities
---

# Glowing Bolt Projectile

This document details the configuration for the "Glowing Bolt" projectile entity in Noita, designed for AI-assisted modding.

## Core Components

The Glowing Bolt is a projectile with moderate speed, a slight tendency to deviate, and an explosive death effect.

### Base Projectile Configuration

This section inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `mass="0.09"`: Defines the projectile's mass.

### Projectile Component

This is the primary component defining the projectile's behavior.

*   **`ProjectileComponent`**:
    *   `speed_min="800"`, `speed_max="900"`: Sets the projectile's initial velocity range.
    *   `direction_random_rad="0.03"`: Introduces a small amount of randomness to the projectile's trajectory.
    *   `on_death_explode="1"`: The projectile explodes upon death.
    *   `on_lifetime_out_explode="1"`: The projectile also explodes when its lifetime expires.
    *   `lifetime="90"`: The base duration of the projectile in frames.
    *   `lifetime_randomness="7"`: Adds variability to the projectile's lifetime.
    *   `damage="0.2"`: The base damage dealt by the projectile.
    *   `knockback_force="2.8"`: The force applied to knock back entities upon collision.
    *   `collide_with_shooter_frames="6"`: The projectile will not collide with its shooter for the first 6 frames.
    *   `friendly_fire="1"`: The projectile can damage friendly entities.
    *   `camera_shake_when_shot="0.4"`: Triggers a small camera shake when the projectile is fired.
    *   `muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher.xml"`: Specifies the particle effect for the muzzle flash.
    *   `shoot_light_flash_r="250"`, `shoot_light_flash_g="250"`, `shoot_light_flash_b="250"`, `shoot_light_flash_radius="100"`: Defines the color and radius of the light flash when the projectile is shot.

#### `config_explosion` (Nested within `ProjectileComponent`)

Defines the properties of the explosion that occurs upon the projectile's death.

*   `damage="0.4"`: The damage dealt by the explosion.
*   `camera_shake="20.0"`: The intensity of camera shake caused by the explosion.
*   `explosion_radius="20"`: The radius of the explosion.
*   `hole_enabled="1"`: Enables the creation of holes in terrain by the explosion.
*   `ray_energy="2050000"`: The energy of the destructive rays emitted by the explosion.
*   `max_durability_to_destroy="11"`: The maximum durability of terrain that can be destroyed by the explosion.
*   `physics_explosion_power.min="0.15"`, `physics_explosion_power.max="0.35"`: The range of physics impulse applied by the explosion.
*   `physics_throw_enabled="1"`: Enables physics-based throwing of objects by the explosion.
*   `sparks_enabled="1"`: Enables the emission of sparks from the explosion.
*   `spark_material="spark_white"`: The material used for the sparks.
*   `stains_enabled="1"`: Enables the creation of stains on surfaces from the explosion.
*   `stains_radius="1"`: The radius of the stains.

### Light Component

Adds a persistent light source to the projectile.

*   **`LightComponent`**:
    *   `radius="150"`: The radius of the light emitted.
    *   `r="180"`, `g="180"`, `b="180"`: The color of the light (a light grey).

### Particle Emitter Components

These components control the visual effects of the projectile.

*   **`ParticleEmitterComponent` (Trail)**:
    *   `emitted_material_name="spark_white"`: The material of the emitted particles.
    *   `is_trail="1"`: Indicates this emitter creates a trail effect.
    *   `emit_cosmetic_particles="1"`: Emits cosmetic particles (visual only).
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="2"`: Controls the frequency of particle emission for the trail.

*   **`ParticleEmitterComponent` (Burst)**:
    *   `emitted_material_name="spark_white"`: The material of the emitted particles.
    *   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime decreases.
    *   `emit_cosmetic_particles="1"`: Emits cosmetic particles.
    *   `emission_interval_min_frames="4"`, `emission_interval_max_frames="8"`: Controls the frequency of particle emission for this burst effect.

### Audio Component

Defines the sound effects associated with the projectile.

*   **`AudioComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: The audio bank containing the sound events.
    *   `event_root="player_projectiles/glowing_bolt"`: The specific sound event for this projectile.

### Variable Storage Component

Stores a reference to the projectile's own XML file.

*   **`VariableStorageComponent`**:
    *   `name="projectile_file"`: The name of the variable.
    *   `value_string="data/entities/projectiles/deck/glowing_bolt.xml"`: The path to this entity's XML file.