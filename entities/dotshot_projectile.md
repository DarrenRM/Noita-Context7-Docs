---
title: Dotshot Projectile
category: entities
---

# Dotshot Projectile

This document details the configuration of the `dotshot.xml` projectile entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Entity Definition

The `dotshot` projectile is a custom entity that inherits base projectile properties and adds unique behaviors and visual effects.

```xml
<Entity 
	name="$projectile_default" 
	>
	<!-- ... other components ... -->
</Entity>
```

## Key Components and Attributes

### Base Projectile Properties

Inherited from `base_projectile.xml`, these define fundamental physics.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="-2"`: A negative value indicates acceleration in air, not friction.
    *   `mass="0.05"`: Defines the projectile's mass.

### Projectile Component

This is the core component defining the projectile's behavior.

*   **`ProjectileComponent`**:
    *   `lob_min="0.8"`, `lob_max="1.0"`: Controls the projectile's lobbing behavior.
    *   `speed_min="150"`, `speed_max="150"`: Sets the projectile's constant speed.
    *   `die_on_low_velocity="0"`: The projectile does not die if its velocity drops too low.
    *   `on_death_explode="1"`: The projectile explodes upon death.
    *   `on_lifetime_out_explode="1"`: The projectile explodes when its lifetime expires.
    *   `damage="0.8"`: The amount of damage dealt by the projectile.
    *   `on_collision_die="1"`: The projectile dies upon colliding with something.
    *   `lifetime="100"`: The duration in frames before the projectile expires.
    *   `knockback_force="1.0"`: The force applied to knock back entities on hit.

#### `config_explosion` (Nested within `ProjectileComponent`)

Defines the properties of the explosion that occurs on death or lifetime out.

*   `never_cache="1"`: Prevents caching of this explosion.
*   `camera_shake="0"`: Disables camera shake from the explosion.
*   `explosion_radius="10"`: The radius of the explosion.
*   `explosion_sprite="data/particles/explosion_016_plasma_green.xml"`: The visual effect for the explosion.
*   `ray_energy="5000"`: Energy value for raycasting effects.
*   `hole_enabled="1"`: Enables the creation of holes in the environment.
*   `hole_image="data/temp/explosion_hole.png"`: The image used for the explosion hole.
*   `physics_explosion_power.min="0.24"`, `physics_explosion_power.max="0.34"`: Controls the physics force of the explosion.
*   `shake_vegetation="1"`: Causes vegetation to shake from the explosion.
*   `light_r="10"`, `light_g="60"`, `light_b="10"`: Defines the RGB color of the explosion's light.

### Sprite Component

Determines the visual appearance of the projectile.

*   **`SpriteComponent`**:
    *   `image_file="data/particles/skullface.xml"`: Specifies the sprite image.
    *   `additive="1"`: Enables additive blending for the sprite.
    *   `emissive="1"`: Makes the sprite emissive, glowing.

### Particle Emitter Component

Manages the emission of particles from the projectile.

*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name="spark_green"`: The material of the emitted particles.
    *   `is_trail="1"`: Indicates that the particles form a trail.
    *   `render_on_grid="1"`: Particles are rendered on the game grid.
    *   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime decreases.
    *   `emit_cosmetic_particles="1"`: Emits cosmetic particles.
    *   `emission_interval_min_frames="5"`, `emission_interval_max_frames="10"`: Controls the frame interval between particle emissions.

### Light Component

Adds a light source to the projectile.

*   **`LightComponent`**:
    *   `radius="150"`: The radius of the light.
    *   `r="30"`, `g="90"`, `b="30"`: Defines the RGB color of the light.

### Audio Component

Handles sound effects for the projectile.

*   **`AudioComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: The audio bank file.
    *   `event_root="projectiles/orb_b"`: The root event for projectile sounds.

### Hit Effect Component

Defines what happens when the projectile hits an entity.

*   **`HitEffectComponent`**:
    *   `effect_hit="LOAD_CHILD_ENTITY"`: Loads a child entity as the hit effect.
    *   `value_string="data/entities/misc/curse_strong_init.xml"`: The path to the entity to load as the hit effect.