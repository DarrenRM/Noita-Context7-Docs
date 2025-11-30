---
title: Fireball Ray Projectile
category: entities
---

# Fireball Ray Projectile

This document details the configuration of the "fireball_ray.xml" entity, which defines a player-fired projectile in Noita. This projectile is a fiery projectile that explodes on impact or after a set duration, leaving behind fire and sparks.

## Core Attributes

The `Entity` tag defines the base properties of the projectile.

*   **`name`**: "$projectile\_default" - Inherits default projectile properties.
*   **`tags`**: "projectile\_player" - Identifies this as a projectile originating from the player.

## Base Projectile Configuration

The `<Base>` tag inherits properties from `data/entities/base_projectile.xml`.

### Velocity Component

*   **`gravity_y`**: "100" - Applies a moderate downward gravitational pull.
*   **`mass`**: "0.09" - Defines the projectile's mass, influencing its interaction with physics.

## Projectile Component

This component defines the specific behaviors and characteristics of the fireball ray.

### Key Attributes:

*   **`lob_min` / `lob_max`**: "0.8" / "1.0" - Controls the arc of the projectile, with a slight upward trajectory.
*   **`speed_min` / `speed_max`**: "160" / "170" - Sets the initial velocity of the projectile.
*   **`die_on_low_velocity`**: "0" - The projectile does not disappear if its speed drops too low.
*   **`on_death_explode`**: "1" - The projectile explodes when it dies.
*   **`on_death_gfx_leave_sprite`**: "0" - No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode`**: "1" - The projectile explodes when its lifetime expires.
*   **`die_on_liquid_collision`**: "1" - The projectile is destroyed upon colliding with liquids.
*   **`damage`**: "0" - Base damage of the projectile itself (before explosion).
*   **`on_collision_die`**: "1" - The projectile dies upon colliding with anything.
*   **`lifetime`**: "60" - The projectile exists for 60 frames before expiring.
*   **`muzzle_flash_file`**: "data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml" - Specifies the visual effect for the muzzle flash.
*   **`shoot_light_flash_r` / `g` / `b` / `radius`**: "255" / "140" / "10" / "150" - Defines the color and radius of the light flash when fired.
*   **`knockback_force`**: "1.5" - The force applied to entities it hits.
*   **`physics_impulse_coeff`**: "2800" - Coefficient for physics impulse, affecting how it interacts with physics objects.

### Damage by Type:

*   **`fire`**: "0.18" - Applies a small amount of fire damage.

### Explosion Configuration (`config_explosion`):

*   **`never_cache`**: "1" - Ensures the explosion effect is always generated fresh.
*   **`camera_shake`**: "7.5" - The intensity of camera shake upon explosion.
*   **`explosion_radius`**: "13" - The radius of the explosion effect.
*   **`explosion_sprite`**: "data/particles/explosion_040_poof.xml" - The visual sprite for the explosion.
*   **`create_cell_probability`**: "100" - Always creates material cells upon explosion.
*   **`create_cell_material`**: "fire" - The material created is fire.
*   **`hole_enabled`**: "1" - Creates a hole in the environment upon explosion.
*   **`damage`**: "1.2" - The damage dealt by the explosion.
*   **`ray_energy`**: "50000" - High energy value, likely for specific ray-based interactions.
*   **`particle_effect`**: "1" - Enables particle effects for the explosion.
*   **`damage_mortals`**: "1" - The explosion damages living entities.
*   **`physics_explosion_power.min` / `max`**: "0.6" / "0.9" - Controls the physics force of the explosion.
*   **`physics_throw_enabled`**: "1" - Entities can be thrown by the explosion.
*   **`shake_vegetation`**: "1" - Causes vegetation to shake.
*   **`sparks_enabled`**: "1" - Generates sparks.
*   **`sparks_count_min` / `max`**: "50" / "100" - The number of sparks generated.
*   **`stains_enabled`**: "1" - Creates stains on surfaces.

## Sprite Component

Defines the visual appearance of the projectile.

*   **`image_file`**: "data/projectiles_gfx/fireball_alt.xml" - The sprite asset used for the fireball.
*   **`offset_x` / `offset_y`**: "16" / "12" - Adjusts the sprite's position.
*   **`additive`**: "1" - The sprite uses additive blending, making it appear brighter.

## Particle Emitters

Multiple `ParticleEmitterComponent` tags are used to create various visual effects.

### Smoke Emitter:

*   **`emitted_material_name`**: "smoke" - Emits smoke particles.
*   **`count_min` / `max`**: "5" / "5" - Emits a consistent number of particles.
*   **`lifetime_min` / `max`**: "0.1" / "0.3" - Short lifespan for smoke particles.
*   **`create_real_particles`**: "1" - Creates actual game particles.

### Spark Emitter:

*   **`emitted_material_name`**: "spark" - Emits spark particles.
*   **`gravity.y`**: "-100.60" - Sparks have an upward initial velocity.
*   **`is_trail`**: "1" - Creates a trail effect.
*   **`render_on_grid`**: "1" - Renders sparks on the game grid.
*   **`fade_based_on_lifetime`**: "1" - Sparks fade out over their lifetime.
*   **`create_real_particles`**: "0" - Emits cosmetic particles.

### Fire Emitter:

*   **`emitted_material_name`**: "fire" - Emits fire particles.
*   **`count_min` / `max`**: "1" / "1" - Emits a single fire particle at a time.
*   **`lifetime_min` / `max`**: "0.1" / "0.3" - Short lifespan for fire particles.

### Sprite Particle Emitter (Orange Smoke):

*   **`sprite_file`**: "data/particles/smoke_orange.xml" - Uses a specific sprite for orange smoke.
*   **`color_change.a`**: "-2" - The alpha (transparency) decreases over time.
*   **`gravity.y`**: "10" - Smoke particles are affected by gravity.
*   **`randomize_position.min_x` / `max_x`**: "2" / "12" - Positions the smoke particles with an offset.
*   **`is_emitting`**: "1" - The emitter is active.

## Light Component

*   **`radius`**: "150" - The projectile emits light with a radius of 150 units.

## Audio Component

*   **`file`**: "data/audio/Desktop/projectiles.bank" - The audio bank containing projectile sounds.
*   **`event_root`**: "player\_projectiles/bullet\_fire\_heavy" - The specific sound event triggered.

## Variable Storage Component

*   **`name`**: "projectile\_file"
*   **`value_string`**: "data/entities/projectiles/deck/fireball\_ray.xml" - Stores the path to this entity's file, likely for internal referencing.