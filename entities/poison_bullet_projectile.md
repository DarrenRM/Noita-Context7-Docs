---
title: Poison Bullet Projectile
category: entities
---

# Poison Bullet Projectile

This document details the configuration of the `bullet_poison.xml` entity, which defines the behavior and appearance of a poison projectile in Noita.

## Core Components

The `bullet_poison.xml` entity is built upon several core Noita components, each contributing to its functionality.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `air_friction`: `1.6` - Controls how quickly the projectile loses velocity in the air.
    *   `mass`: `0.065` - The mass of the projectile, influencing its momentum.

### Projectile Behavior (`ProjectileComponent`)

This is the primary component defining the projectile's unique characteristics.

*   **Key Attributes**:
    *   `lob_min`, `lob_max`: `0.8`, `1.4` - Controls the arc of the projectile.
    *   `speed_min`, `speed_max`: `450`, `550` - The initial speed range of the projectile.
    *   `friction`: `1` - How much friction affects the projectile's speed.
    *   `direction_random_rad`: `0.05` - Introduces a small random deviation in the projectile's direction.
    *   `on_death_explode`: `1` - The projectile explodes upon death.
    *   `on_lifetime_out_explode`: `1` - The projectile explodes when its lifetime expires.
    *   `on_collision_die`: `1` - The projectile is destroyed upon collision.
    *   `lifetime`: `40` - The base lifetime of the projectile in frames.
    *   `lifetime_randomness`: `7` - Adds randomness to the projectile's lifetime.
    *   `damage`: `0.33` - The base damage dealt by the projectile.
    *   `knockback_force`: `0.7` - The force applied to knock back entities upon impact.
    *   `camera_shake_when_shot`: `0.4` - The amount of camera shake when this projectile is fired.
    *   `create_shell_casing`: `1` - Creates a shell casing when fired.
    *   `muzzle_flash_file`: `data/entities/particles/muzzle_flashes/muzzle_flash_magic_large.xml` - Specifies the muzzle flash particle effect.

*   **`config_explosion`**: Defines the properties of the explosion when the projectile dies or its lifetime ends.
    *   `damage`: `0.25` - Damage dealt by the explosion.
    *   `camera_shake`: `0.5` - Camera shake caused by the explosion.
    *   `explosion_radius`: `3` - The radius of the explosion.
    *   `hole_enabled`: `1` - Enables the creation of holes in terrain.
    *   `ray_energy`: `60000` - The energy of the explosion's rays.
    *   `physics_explosion_power.min`, `physics_explosion_power.max`: `0.3`, `0.4` - The minimum and maximum physics force of the explosion.
    *   `shake_vegetation`: `1` - Causes vegetation to shake from the explosion.
    *   `stains_enabled`: `1` - Enables the creation of stains from the explosion.
    *   `stains_radius`: `1` - The radius of the stains.

### Visual Representation (`SpriteComponent`)

This component defines the projectile's visual appearance.

*   **Key Attributes**:
    *   `image_file`: `data/projectiles_gfx/heavy_bullet_poison.xml` - The sprite file used for the projectile.
    *   `offset_x`, `offset_y`: `2`, `2` - Offsets for the sprite's position.
    *   `emissive`: `1` - Makes the sprite emissive (glows).
    *   `additive`: `1` - Uses additive blending for the sprite, often for glowing effects.

### Particle Emission (`ParticleEmitterComponent`)

This component controls the emission of particles, in this case, poison particles.

*   **Key Attributes**:
    *   `emitted_material_name`: `poison` - The material of the particles to be emitted.
    *   `offset.x`, `offset.y`: `-1`, `0` - Offset for the particle emitter's position.
    *   `x_vel_min`, `x_vel_max`: `-10`, `10` - The range of horizontal velocity for emitted particles.
    *   `y_vel_min`, `y_vel_max`: `0`, `0` - The range of vertical velocity for emitted particles.
    *   `count_min`, `count_max`: `5`, `9` - The number of particles emitted per burst.
    *   `lifetime_min`, `lifetime_max`: `0.3`, `1.6` - The lifetime range of emitted particles.
    *   `is_emitting`: `1` - Enables particle emission.

### Audio (`AudioComponent`)

Defines the sound effects associated with the projectile.

*   **Key Attributes**:
    *   `file`: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
    *   `event_root`: `projectiles/poison` - The root event name for poison projectile sounds.

### Variable Storage (`VariableStorageComponent`)

Stores variables associated with the entity.

*   **Key Attributes**:
    *   `name`: `projectile_file` - The name of the variable.
    *   `value_string`: `data/entities/projectiles/bullet_poison.xml` - The string value, referencing the entity's own file.