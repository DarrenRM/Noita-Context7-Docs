---
title: Tiny Orb Projectile
category: entities
---

# Tiny Orb Projectile

This document details the configuration for the "Tiny Orb" projectile entity in Noita, focusing on its behavior, visual representation, and particle effects.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="-0.7"`: A slight air friction is applied.
    *   `terminal_velocity="200"`: Sets a maximum speed due to air resistance.
    *   `mass="0.8"`: Defines the projectile's mass.

### Homing Component (`<HomingComponent>`)

Enables the projectile to track its target.

*   `just_rotate_towards_target="1"`: The projectile will only rotate to face the target, not change its velocity direction directly.
*   `max_turn_rate="0.015"`: Controls how quickly the projectile can turn towards its target.

### Projectile Component (`<ProjectileComponent>`)

Defines the specific behaviors and properties of this projectile.

*   **Movement & Trajectory**:
    *   `lob_min="0.8"`, `lob_max="1.0"`: Controls the arc of the projectile.
    *   `speed_min="50"`, `speed_max="50"`: The projectile travels at a fixed speed of 50.
    *   `direction_random_rad="3.14151"`: Introduces significant randomness in the initial direction.
    *   `die_on_low_velocity="0"`: The projectile does not die if its velocity becomes too low.
    *   `on_death_explode="1"`: The projectile explodes upon death.
    *   `on_lifetime_out_explode="1"`: The projectile explodes when its lifetime expires.
    *   `bounces_left="1"`: The projectile can bounce once.
    *   `bounce_at_any_angle="1"`: The projectile can bounce regardless of the collision angle.
    *   `bounce_energy="0.8"`: Retains 80% of its energy after a bounce.
*   **Damage & Effects**:
    *   `damage="0.12"`: The projectile deals a small amount of damage.
    *   `on_collision_die="1"`: The projectile dies upon colliding with something.
    *   `knockback_force="0.1"`: Applies a small knockback force.
*   **Lifetime**:
    *   `lifetime="130"`: The base lifetime of the projectile in frames.
    *   `lifetime_randomness="50"`: Adds randomness to the projectile's lifetime.
*   **Explosion Configuration (`<config_explosion>`)**:
    *   `never_cache="1"`: Prevents caching of this explosion effect.
    *   `camera_shake="0.0"`: No camera shake is applied.
    *   `explosion_radius="6"`: The radius of the explosion.
    *   `explosion_sprite="data/particles/explosion_008_pink.xml"`: The visual sprite for the explosion.
    *   `create_cell_probability="1"`: Always creates a cell upon explosion.
    *   `create_cell_material="plasma_fading_pink"`: The material of the created cell.
    *   `ray_energy="10000"`: High energy for potential ray interactions.
    *   `hole_destroy_liquid="1"`: The explosion can destroy liquids.
    *   `hole_enabled="1"`: Creates a hole in terrain.
    *   `damage="0"`: The explosion itself does not deal direct damage.
    *   `physics_explosion_power.min="0.4"`, `physics_explosion_power.max="0.6"`: The force applied to physics objects.
    *   `sparks_enabled="1"`: Sparks are generated.
    *   `spark_material="plasma_fading_pink"`: The material of the sparks.
    *   `light_r="155"`, `light_g="15"`, `light_b="140"`: Defines the color of the light emitted by the explosion.
    *   `stains_enabled="1"`: Creates stains on surfaces.

### Set Start Velocity Component (`<SetStartVelocityComponent>`)

Determines the initial velocity of the projectile.

*   `randomize_speed.min="200"`, `randomize_speed.max="400"`: The initial speed is randomized between 200 and 400.
*   `randomize_angle.min="0"`, `randomize_angle.max="3.1"`: The initial direction is randomized within a wide angle.

### Sprite Component (`<SpriteComponent>`)

Defines the visual appearance of the projectile.

*   `image_file="data/projectiles_gfx/orb_tiny.xml"`: Specifies the sprite file for the projectile.
*   `additive="1"`: The sprite uses additive blending for a glowing effect.

## Particle Emitters

### Trail Emitter (`<ParticleEmitterComponent>`)

Generates a visual trail behind the projectile.

*   `emitted_material_name="plasma_fading_pink"`: The material of the trail particles.
*   `lifetime_min="0.05"`, `lifetime_max="1.15"`: The duration of each trail particle.
*   `emission_interval_min_frames="2"`, `emission_interval_max_frames="2"`: Particles are emitted every 2 frames.
*   `is_trail="0"`: While named "trail", this specific emitter is not configured as a continuous trail.
*   `emit_cosmetic_particles="1"`: Emits cosmetic particles.

### Poof Emitter (`<ParticleEmitterComponent>`)

Creates a burst of particles upon the projectile's death or expiration.

*   `emitted_material_name="plasma_fading_pink"`: The material of the poof particles.
*   `emitter_lifetime_frames="2"`: The emitter itself is active for a very short duration.
*   `area_circle_radius.min="3"`, `area_circle_radius.max="3"`: Particles are emitted from a small circular area.
*   `velocity_always_away_from_center="40"`: Particles are pushed outwards from the center.
*   `lifetime_min="0.5"`, `lifetime_max="2.0"`: The duration of each poof particle.
*   `emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`: Particles are emitted every frame during the emitter's lifetime.
*   `emit_cosmetic_particles="1"`: Emits cosmetic particles.

## Variable Storage

### Projectile File (`<VariableStorageComponent>`)

Stores the path to this projectile's XML file.

*   `name="projectile_file"`: The name of the variable.
*   `value_string="data/entities/projectiles/orb_tiny.xml"`: The value, pointing to this entity's definition.