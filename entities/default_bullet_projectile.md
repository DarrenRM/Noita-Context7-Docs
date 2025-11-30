---
title: Default Bullet Projectile
category: entities
---

# Default Bullet Projectile

This document details the configuration of the default bullet projectile in Noita, commonly found in the `data/entities/projectiles/deck/bullet.xml` file. This projectile serves as a foundational element for many player-fired projectiles.

## Core Components

The `bullet.xml` entity is built upon several key components that define its behavior, appearance, and effects.

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="200"`: Applies a moderate downward gravitational pull.
    *   `air_friction="1.2"`: Modifies air resistance.
    *   `mass="0.07"`: Defines the projectile's mass.

### Projectile Behavior (`<ProjectileComponent>`)

This is the primary component defining the projectile's unique characteristics.

*   **`lob_min="0.5"`, `lob_max="0.7"`**: Controls the minimum and maximum "lob" or arc of the projectile.
*   **`speed_min="600"`, `speed_max="650"`**: Sets the range for the projectile's initial speed.
*   **`friction="1"`**: Governs how quickly the projectile loses speed due to friction.
*   **`direction_random_rad="0.01"`**: Introduces a slight random deviation in the projectile's trajectory.
*   **`on_death_explode="1"`**: Causes the projectile to explode upon expiring or colliding.
*   **`on_lifetime_out_explode="1"`**: Ensures an explosion occurs when the projectile's lifetime ends.
*   **`explosion_dont_damage_shooter="1"`**: Prevents the projectile's explosion from harming the entity that fired it.
*   **`on_collision_die="1"`**: The projectile is destroyed upon hitting a surface.
*   **`lifetime="40"`**: The base duration of the projectile in frames.
*   **`lifetime_randomness="7"`**: Adds variability to the projectile's lifetime.
*   **`damage="0.40"`**: The base damage dealt by the projectile.
*   **`knockback_force="1.8"`**: The force applied to entities hit by the projectile.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_laser_green.xml"`**: Specifies the visual effect at the point of firing.
*   **`shoot_light_flash_radius="72"`**: The radius of the light emitted when the projectile is fired.

#### Explosion Configuration (`<config_explosion>`)

Defines the properties of the explosion triggered by the projectile.

*   **`damage="0"`**: The explosion itself does not deal direct damage (damage is handled by the projectile's `damage` attribute).
*   **`camera_shake="0.5"`**: The intensity of camera shake upon explosion.
*   **`explosion_radius="2"`**: The area of effect for the explosion.
*   **`hole_enabled="1"`**: Allows the explosion to create holes in terrain.
*   **`ray_energy="400000"`**: The energy of the destructive rays emitted by the explosion.
*   **`max_durability_to_destroy="8"`**: The maximum durability of terrain that can be destroyed by the explosion.
*   **`physics_explosion_power.min="0.02"`, `physics_explosion_power.max="0.1"`**: Controls the force of the physics-based explosion.
*   **`light_enabled="1"`**: Enables a light source at the explosion's origin.
*   **`stains_enabled="1"`**: Creates stains on surfaces hit by the explosion.

### Visuals (`<SpriteComponent>`)

Determines the projectile's appearance.

*   **`image_file="data/projectiles_gfx/light_arrow.xml"`**: The sprite asset used for the projectile.
*   **`additive="1"`**: Enables additive blending for the sprite, often used for glowing effects.

### Particle Effects (`<ParticleEmitterComponent>`)

Manages the emission of particles, such as trails.

*   **`emitted_material_name="spark_green"`**: The material of the particles emitted.
*   **`is_trail="1"`**: Indicates that these particles form a trail.
*   **`count_min="1"`, `count_max="1"`**: The number of particles emitted per emission.
*   **`lifetime_min="1.0"`, `lifetime_max="1.5"`**: The duration of emitted particles.

### Audio (`<AudioComponent>`)

Handles sound effects associated with the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound events.
*   **`event_root="player_projectiles/bullet"`**: The specific sound event for this projectile.

### Lighting (`<LightComponent>`)

Adds a light source to the projectile itself.

*   **`radius="40"`**: The radius of the light emitted by the projectile.
*   **`r="40"`, `g="120"`, `b="10"`**: The color of the light.

### Variable Storage (`<VariableStorageComponent>`)

Used to store and reference variables.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/deck/bullet.xml"`**: The value, pointing to the projectile's own XML file.