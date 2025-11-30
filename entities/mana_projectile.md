---
title: Mana Projectile
category: entities
---

# Mana Projectile

This document describes the `mana.xml` entity, which defines the behavior and appearance of the Mana projectile in Noita.

## ProjectileComponent

This component governs the core projectile mechanics.

### Key Attributes:

*   `speed_min`, `speed_max`: Set to `0`, indicating the projectile does not have inherent velocity upon creation.
*   `die_on_low_velocity`: `1` (enabled), the projectile will disappear if its speed drops too low.
*   `on_death_explode`: `0` (disabled), the projectile does not explode upon death.
*   `on_lifetime_out_explode`: `1` (enabled), the projectile explodes when its lifetime expires.
*   `on_collision_die`: `1` (enabled), the projectile is destroyed upon collision.
*   `damage`: `0`, this projectile deals no direct damage.
*   `lifetime`: `10` seconds, the duration before the projectile explodes if it hasn't collided.
*   `shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`: Define the RGB color of the light flash when the projectile is shot (40, 140, 190 - a bluish tint).
*   `shoot_light_flash_radius`: `120`, the radius of the light flash.

### `config_explosion` (Nested within `ProjectileComponent`)

Defines the explosion properties when `on_lifetime_out_explode` is triggered.

*   `damage`: `0`, the explosion deals no damage.
*   `camera_shake`: `0`, no camera shake is applied.
*   `explosion_radius`: `1`, a very small explosion radius.
*   `explosion_sprite`: `data/particles/explosion_016_plasma.xml`, uses a plasma explosion visual.
*   `physics_explosion_power.min`, `physics_explosion_power.max`: Set to `0`, no physics force is applied by the explosion.
*   `hole_enabled`: `0`, the explosion does not create holes.
*   `particle_effect`: `0`, no specific particle effect is created by the explosion itself.

## ParticleEmitterComponent (First Instance)

This component is responsible for emitting cosmetic particles that form the visual trail of the Mana projectile.

### Key Attributes:

*   `emitted_material_name`: `plasma_fading`, the material used for the emitted particles.
*   `gravity.y`: `0.0`, particles are not affected by gravity.
*   `area_circle_radius.min`, `area_circle_radius.max`: `12`, particles are emitted within a 12-unit radius circle.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: `-30` to `30`, particles are given a random velocity.
*   `count_min`, `count_max`: `100` to `120`, a large number of particles are emitted per interval.
*   `lifetime_min`, `lifetime_max`: `1.8` to `3.0` seconds, the duration particles exist.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These attributes influence how particles react to air currents, creating a subtle trailing effect.
*   `emit_cosmetic_particles`: `1` (enabled), ensures these are visual-only particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `1`, particles are emitted continuously.
*   `is_emitting`: `1` (enabled).

## ParticleEmitterComponent (Second Instance)

This component emits a smaller, more persistent set of cosmetic particles, likely for the core visual of the mana itself.

### Key Attributes:

*   `emitted_material_name`: `plasma_fading`.
*   `gravity.y`: `0.0`.
*   `lifetime_min`, `lifetime_max`: `6` to `8` seconds, these particles last longer.
*   `count_min`, `count_max`: `3`, a small number of particles are emitted.
*   `fade_based_on_lifetime`: `1` (enabled), particles fade out as their lifetime decreases.
*   `area_circle_radius.min`, `area_circle_radius.max`: `0`, particles are emitted from a single point.
*   `cosmetic_force_create`: `0`.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Similar to the first emitter, influencing particle movement.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `1`.
*   `emit_cosmetic_particles`: `1` (enabled).
*   `image_animation_file`: `data/particles/image_emitters/mana.png`, uses a specific animated sprite for emission.
*   `image_animation_speed`: `5`.
*   `image_animation_loop`: `0` (disabled), the animation plays once.
*   `is_emitting`: `1` (enabled).

## VelocityComponent

An empty `VelocityComponent` is present, indicating that the projectile's initial velocity is managed by other components or game logic, rather than being directly defined here.

## VariableStorageComponent

*   `name`: `projectile_file`
*   `value_string`: `data/entities/projectiles/deck/mana.xml`
    This component stores a reference to the entity's own file path, which can be useful for scripting or other entities that interact with this projectile.