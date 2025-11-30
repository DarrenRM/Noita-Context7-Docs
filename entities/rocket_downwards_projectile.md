---
title: Rocket Downwards Projectile
category: entities
---

# Rocket Downwards Projectile

This document details the configuration for the "rocket_downwards.xml" projectile entity in Noita, designed for AI-assisted modding.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="200"`: Applies a significant downward gravitational pull.
    *   `air_friction="-0.5"`: Introduces air resistance, slowing the projectile.
    *   `mass="0.05"`: Defines the projectile's mass.

### Projectile Component (`<ProjectileComponent>`)

This is the primary component defining the projectile's behavior and effects.

*   **`_enabled="1"`**: Enables the component.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the projectile's arc, with a slight tendency towards a straight trajectory.
*   **`speed_min="70"`, `speed_max="100"`**: Sets the initial velocity range.
*   **`direction_random_rad="0.0"`**: Ensures the projectile travels in a precise direction without random deviation.
*   **`on_death_explode="1"`**: Triggers an explosion upon death (e.g., hitting a surface or expiring).
*   **`on_death_gfx_leave_sprite="0"`**: The projectile's sprite does not persist after death.
*   **`on_lifetime_out_explode="1"`**: Explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="0"`**: The explosion can damage the shooter.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision.
*   **`lifetime="360"`**: The projectile exists for 360 frames before expiring.
*   **`damage="1.3"`**: The base damage dealt by the projectile.
*   **`collide_with_shooter_frames="1"`**: The projectile can collide with the shooter within the first frame.
*   **`friendly_fire="1"`**: The projectile can damage allies.
*   **`velocity_sets_scale="1"`**: Velocity influences the scale of certain effects.
*   **`lifetime_randomness="7"`**: Adds a small random variation to the projectile's lifetime.
*   **`knockback_force="3.0"`**: The force applied to knock back entities on impact.
*   **`physics_impulse_coeff="3000"`**: Coefficient for physics impulse calculations.
*   **`camera_shake_when_shot="15.0"`**: Triggers camera shake when the projectile is fired.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_launcher.xml"`**: Specifies the muzzle flash particle effect.
*   **`shoot_light_flash_r="215"`, `shoot_light_flash_g="40"`, `shoot_light_flash_b="255"`, `shoot_light_flash_radius="90"`**: Defines the color and radius of the light flash when shot.

#### Explosion Configuration (`<config_explosion>`)

Defines the properties of the explosion triggered by the projectile.

*   **`never_cache="1"`**: Prevents caching of this explosion.
*   **`camera_shake="20"`**: The intensity of camera shake during the explosion.
*   **`explosion_radius="12"`**: The radius of the explosion's effect.
*   **`explosion_sprite="data/particles/explosion_016_plasma_pink.xml"`**: The sprite used for the explosion visual.
*   **`load_this_entity="data/entities/particles/particle_explosion/main_swirly_purple_small.xml"`**: The entity to load for the explosion effect.
*   **`explosion_sprite_lifetime="0"`**: The explosion sprite has no independent lifetime.
*   **`create_cell_probability="10"`**: Probability of creating cell-like effects.
*   **`cell_explosion_power_ragdoll_coeff="0.5"`**: Coefficient for ragdoll force from cell explosions.
*   **`hole_enabled="1"`**: Creates holes in terrain.
*   **`ray_energy="4000000"`**: The energy of destructive rays emitted by the explosion.
*   **`damage="1.4"`**: Damage dealt by the explosion itself.
*   **`physics_explosion_power.min="1.0"`, `physics_explosion_power.max="1.4"`**: Minimum and maximum physics force of the explosion.
*   **`physics_throw_enabled="1"`**: Entities can be thrown by the explosion.
*   **`shake_vegetation="1"`**: Vegetation is affected by the explosion.
*   **`sparks_count_min="7"`, `sparks_count_max="20"`**: Number of sparks generated.
*   **`spark_material="plasma_fading_pink"`**: The material of the sparks.
*   **`stains_enabled="1"`**: Creates stains on surfaces.
*   **`stains_radius="15"`**: The radius of the stains.
*   **`audio_event_name="explosions/magic_rocket_small"`**: The sound event triggered by the explosion.

### Sprite Component (`<SpriteComponent>`)

Defines the visual appearance of the projectile.

*   **`image_file="data/projectiles_gfx/fireball_small.xml"`**: The sprite asset used for the projectile.

### Light Component (`<LightComponent>`)

Adds a light source to the projectile.

*   **`r="180"`, `g="40"`, `b="255"`**: The RGB color of the light.
*   **`radius="150"`**: The radius of the light emitted.

### Particle Emitter Components (`<ParticleEmitterComponent>`)

These components generate various particle effects.

*   **Smoke Emitter**:
    *   `emitted_material_name="smoke"`: Emits smoke particles.
    *   `count_min="5"`, `count_max="5"`: Emits a fixed number of particles.
    *   `lifetime_min="0.1"`, `lifetime_max="0.3"`: Short lifetime for smoke particles.
*   **Spark Emitters (Multiple)**:
    *   `emitted_material_name="spark_purple_bright"`: Emits bright purple sparks.
    *   `is_trail="1"`: Creates a trail effect.
    *   `gravity.y` varies (`10`, `-10`, `0.0`): Controls the vertical direction of spark trails.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="2"`: Frequent emission.
*   **Sparse Spark Emitter**:
    *   `emitted_material_name="spark_purple_bright"`: Emits bright purple sparks.
    *   `emission_interval_min_frames="8"`, `emission_interval_max_frames="12"`: Less frequent emission for a sparser effect.
    *   `lifetime_min="1.4"`, `lifetime_max="1.5"`: Longer lifetime for these sparks.

### Audio Component (`<AudioComponent>`)

Handles the sound effects for the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound.
*   **`event_root="player_projectiles/bullet_rocket_magic"`**: The specific sound event to play.

### Variable Storage Component (`<VariableStorageComponent>`)

Stores variables associated with the entity.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/deck/rocket_downwards.xml"`**: The value, pointing to the entity's own file path.