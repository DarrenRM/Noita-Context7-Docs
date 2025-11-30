---
title: Laser Spear Projectile
category: entities
---

# Laser Spear Projectile

This document details the configuration of the `laser_spear.xml` entity, which defines the behavior and appearance of the laser spear projectile in Noita.

## Core Components

The `laser_spear.xml` entity is built upon several core Noita components, each contributing to its functionality.

### Base Projectile (`BaseComponent`)

Inherits fundamental projectile properties.

*   **`air_friction`**: `-0.4` - Controls how much air resistance affects the projectile.
*   **`mass`**: `0.65` - Defines the projectile's mass, influencing its momentum and interaction with physics.

### Projectile Behavior (`ProjectileComponent`)

This is the primary component defining the projectile's unique characteristics.

*   **`_enabled`**: `1` - Ensures the component is active.
*   **`lob_min` / `lob_max`**: `0.8` / `1.1` - Controls the minimum and maximum "lob" or arc of the projectile.
*   **`speed_min` / `speed_max`**: `500` / `600` - Sets the projectile's initial velocity range.
*   **`direction_random_rad`**: `0.003` - Introduces a slight random deviation in the projectile's trajectory.
*   **`on_death_explode`**: `1` - The projectile will explode upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile will explode when its lifetime expires.
*   **`die_on_low_velocity`**: `1` - The projectile will be destroyed if its velocity drops too low.
*   **`on_collision_die`**: `1` - The projectile will be destroyed upon colliding with an entity.
*   **`lifetime`**: `300` - The duration in frames before the projectile expires.
*   **`ground_penetration_coeff`**: `6` - How effectively the projectile penetrates the ground.
*   **`velocity_sets_scale`**: `1` - Whether the projectile's velocity affects its scale.
*   **`shoot_light_flash_radius`**: `140` - The radius of the light flash when the projectile is shot.
*   **`shoot_light_flash_r` / `g` / `b`**: `155` / `235` / `255` - The RGB color values for the shooting light flash.
*   **`knockback_force`**: `1.1` - The force applied to entities when the projectile hits them.
*   **`damage`**: `0` - Base damage value.
*   **`friendly_fire`**: `1` - Allows the projectile to damage the shooter.
*   **`collide_with_shooter_frames`**: `6` - Frames the projectile is immune to colliding with the shooter.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_magic_large.xml` - Specifies the particle effect for the muzzle flash.

#### Damage by Type (`damage_by_type`)

*   **`holy`**: `1.2` - Applies a multiplier to holy damage.

#### Explosion Configuration (`config_explosion`)

Defines the parameters for the projectile's explosion.

*   **`damage`**: `0` - Damage dealt by the explosion.
*   **`camera_shake`**: `0` - Disables camera shake from the explosion.
*   **`explosion_radius`**: `1` - The radius of the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_016_plasma.xml` - The visual sprite for the explosion.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the explosion hole.
*   **`ray_energy`**: `100000` - The energy of rays emitted by the explosion.
*   **`physics_explosion_power.min` / `max`**: `0` / `0` - Disables physics-based explosion force.
*   **`shake_vegetation`**: `1` - Causes vegetation to shake during the explosion.
*   **`sparks_enabled`**: `1` - Enables sparks during the explosion.
*   **`spark_material`**: `spark_blue` - The material used for sparks.
*   **`light_enabled`**: `1` - Enables light emission from the explosion.
*   **`light_r` / `g` / `b`**: `40` / `120` / `180` - RGB color values for the explosion light.
*   **`stains_enabled`**: `1` - Enables stains on surfaces from the explosion.
*   **`stains_radius`**: `1` - The radius of the stains.

### Particle Emitter (`ParticleEmitterComponent`)

Manages the visual particles emitted by the projectile.

*   **`emitted_material_name`**: `spark_blue` - The material of the emitted particles.
*   **`gravity.y`**: `0.10` - The gravitational pull on the particles.
*   **`x_vel_min` / `max`**: `-10` / `10` - The horizontal velocity range of particles.
*   **`y_vel_min` / `max`**: `0` / `0` - The vertical velocity range of particles.
*   **`count_min` / `max`**: `1` / `5` - The number of particles emitted per burst.
*   **`lifetime_min` / `max`**: `0.6` / `5.8` - The lifespan of emitted particles.
*   **`is_trail`**: `1` - Indicates that these particles form a trail.
*   **`trail_gap`**: `1.0` - The spacing between trail particles.
*   **`airflow_force`**: `0.1` - The force of airflow affecting particles.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`emit_cosmetic_particles`**: `1` - Emits particles that are purely visual.
*   **`is_emitting`**: `1` - The emitter is active.

### Light Component (`LightComponent`)

Adds a light source to the projectile.

*   **`radius`**: `60` - The radius of the light.
*   **`r` / `g` / `b`**: `30` / `100` / `180` - The RGB color values for the light.

### Audio Component (`AudioComponent`)

Handles sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   **`event_root`**: `player_projectiles/bullet_arrow` - The root event for player projectile sounds.

### Variable Storage (`VariableStorageComponent`)

Stores custom variables for the entity.

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/laser_spear.xml` - Stores the path to this entity's XML file.