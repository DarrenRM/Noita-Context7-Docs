---
title: Slime Boss Limb Projectile
category: entities
---

# Slime Boss Limb Projectile

This entity defines a projectile used by a slime boss, characterized by its explosive death and the creation of radioactive liquid cells.

## Key Components and Attributes

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

*   **`VelocityComponent`**:
    *   `gravity_y="10"`: Applies a moderate downward gravity.
    *   `air_friction="0"`: No air resistance.

### Projectile Behavior (`ProjectileComponent`)

*   `_enabled="1"`: Component is active.
*   `speed_min="100"`, `speed_max="105"`: Defines the projectile's speed range.
*   `on_death_explode="1"`: The projectile explodes when it dies.
*   `on_lifetime_out_explode="1"`: The projectile explodes when its lifetime expires.
*   `on_collision_die="1"`: The projectile dies upon collision.
*   `die_on_low_velocity="1"`: The projectile dies if its velocity drops too low.
*   `damage="0.3"`: Base damage dealt by the projectile itself.
*   `lifetime="430"`: Duration in frames before the projectile expires.

#### Explosion Configuration (`config_explosion`)

*   `never_cache="1"`: Prevents caching of this explosion.
*   `damage="0.35"`: Damage dealt by the explosion.
*   `camera_shake="3.5"`: Intensity of camera shake upon explosion.
*   `explosion_radius="5"`: The radius of the explosion.
*   `explosion_sprite="data/particles/explosion_032_slimeburst.xml"`: Visual effect for the explosion.
*   `explosion_sprite_lifetime="0.34"`: Duration of the explosion sprite.
*   `create_cell_probability="5"`: Probability of creating material cells.
*   `create_cell_material="radioactive_liquid_fading"`: The material of the cells created.
*   `hole_enabled="1"`: Creates holes in terrain upon explosion.
*   `hole_image="data/temp/explosion_hole.png"`: Image used for the explosion hole.
*   `physics_explosion_power.max="0.9"`: Maximum physics force applied by the explosion.
*   `stains_enabled="1"`: Creates stains on surfaces.
*   `stains_radius="9"`: Radius of the stains.

### Visuals (`SpriteComponent`)

*   `image_file="data/projectiles_gfx/slimeball_small.xml"`: The sprite asset for the projectile.
*   `offset_x="8"`, `offset_y="6"`: Adjusts the sprite's position.

### Particle Emission (`ParticleEmitterComponent`)

*   `emitted_material_name="radioactive_liquid_fading"`: The material of the emitted particles.
*   `count_min="1"`, `count_max="2"`: Number of particles emitted per burst.
*   `x_vel_min="-50"`, `x_vel_max="50"`: Horizontal velocity range of particles.
*   `y_vel_min="-50"`, `y_vel_max="50"`: Vertical velocity range of particles.
*   `lifetime_min="0.1"`, `lifetime_max="0.3"`: Duration of emitted particles.
*   `is_emitting="1"`: The emitter is active.

### Lighting (`LightComponent`)

*   `radius="30"`: The radius of the light emitted.
*   `r="99"`, `g="205"`, `b="139"`: RGB color of the light (a greenish hue).
*   `offset_y="-9"`: Vertical offset for the light source.

### Hitbox (`HitboxComponent`)

*   `aabb_min_x="-3"`, `aabb_max_x="3"`: Defines the horizontal bounds of the hitbox.
*   `aabb_min_y="-3"`, `aabb_max_y="3"`: Defines the vertical bounds of the hitbox.

### Damage Model (`DamageModelComponent`)

*   `hp="0.17"`: Hit points of the projectile.
*   `blood_material="radioactive_liquid_fading"`: The material that acts as "blood" when damaged.
*   `blood_multiplier="0"`: No multiplier for blood effects.