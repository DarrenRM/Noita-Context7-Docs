---
title: Rocket Drone Projectile
category: entities
---

# Rocket Drone Projectile

This document details the `rocket_drone.xml` entity, which defines the behavior and appearance of a rocket projectile, likely fired by a drone.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `mass`: `0.04` - Defines the projectile's mass.

### Projectile Component (`ProjectileComponent`)

This is the primary component governing the projectile's flight, damage, and death effects.

*   **Flight Dynamics**:
    *   `speed_min`/`speed_max`: `190`/`220` - Sets the projectile's initial velocity range.
    *   `lob_min`/`lob_max`: `0.8`/`1.0` - Controls the arc or lob of the projectile.
    *   `friction`: `-2.0` - Affects how quickly the projectile loses velocity (negative values can imply acceleration or unusual drag).
    *   `direction_random_rad`: `0.05` - Introduces slight randomness to the projectile's initial direction.
    *   `bounces_left`: `1` - The projectile can bounce once before expiring.
*   **Death & Explosion**:
    *   `on_death_explode`: `1` - The projectile explodes upon death.
    *   `on_lifetime_out_explode`: `1` - The projectile explodes when its lifetime expires.
    *   `on_collision_die`: `1` - The projectile is destroyed upon collision.
    *   `lifetime`: `60` - The maximum duration of the projectile in frames.
    *   `lifetime_randomness`: `7` - Adds variability to the projectile's lifetime.
*   **Damage & Effects**:
    *   `damage`: `0.2` - Base damage dealt by the projectile itself.
    *   `explosion_dont_damage_shooter`: `1` - Prevents the explosion from harming the entity that fired it.
    *   `knockback_force`: `2.0` - The force applied to entities hit by the projectile's explosion.
    *   `camera_shake_when_shot`: `5.0` - The intensity of camera shake when this projectile is fired.
*   **Visuals & Particles**:
    *   `muzzle_flash_file`: `data/entities/particles/muzzle_flashes/muzzle_flash_launcher.xml` - Specifies the particle effect for the muzzle flash.

#### Explosion Configuration (`config_explosion`)

Defines the parameters of the explosion when the projectile detonates.

*   `explosion_radius`: `10` - The radius of the explosion's effect.
*   `explosion_sprite`: `data/particles/explosion_016.xml` - The visual sprite used for the explosion.
*   `explosion_sprite_emissive`/`additive`: `1` - Controls how the explosion sprite is rendered (emissive and additive).
*   `hole_enabled`: `1` - Creates a hole in terrain upon explosion.
*   `ray_energy`: `40000` - The energy of the explosion's damaging rays.
*   `damage`: `0.5` - Damage dealt by the explosion.
*   `physics_explosion_power.min`/`max`: `0.6`/`0.8` - The minimum and maximum force of the physics-based explosion.
*   `sparks_count_min`/`max`: `7`/`20` - The range for the number of sparks generated.
*   `stains_radius`: `15` - The radius of stains left by the explosion.

### Sprite Component (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   `image_file`: `data/projectiles_gfx/fireball_small.xml` - The texture file for the projectile's sprite.
*   `emissive`: `1` - Makes the sprite emit light.
*   `offset_x`/`offset_y`: `2`/`2` - Adjusts the sprite's position.

### Light Component (`LightComponent`)

Adds a light source to the projectile.

*   `r`/`g`/`b`: `255`/`100`/`10` - Defines the color of the light (orange/reddish).
*   `radius`: `150` - The radius of the light emitted.

### Particle Emitters (`ParticleEmitterComponent`)

These components generate secondary particle effects.

*   **Smoke Emitter**:
    *   `emitted_material_name`: `smoke` - Generates smoke particles.
    *   `count_min`/`max`: `5`/`5` - Emits a fixed number of particles.
    *   `lifetime_min`/`max`: `0.1`/`0.3` - Short lifespan for smoke particles.
*   **Spark Emitter**:
    *   `emitted_material_name`: `spark` - Generates spark particles.
    *   `count_min`/`max`: `1`/`2` - Emits a small number of sparks.
    *   `lifetime_min`/`max`: `0.3`/`0.4` - Lifespan for spark particles.
    *   `create_real_particles`: `0` - These are cosmetic particles.

### Audio Components

*   **`AudioLoopComponent`**:
    *   `event_name`: `projectiles/rocket_passby` - Plays a looping sound effect during flight.
*   **`AudioComponent`**:
    *   `event_root`: `projectiles/rocket` - Plays a root sound event, likely on impact or death.

### Variable Storage (`VariableStorageComponent`)

*   `name`: `projectile_file`
*   `value_string`: `data/entities/projectiles/rocket_drone.xml` - Stores the entity's own file path, useful for referencing itself.