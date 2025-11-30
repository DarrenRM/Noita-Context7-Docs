---
title: Air Bullet Projectile
category: entities
---

# Air Bullet Projectile

This document describes the `air_bullet.xml` entity, which defines the behavior and appearance of a basic air projectile in Noita.

## Core Functionality

The `air_bullet.xml` entity is a projectile with specific properties related to its movement, impact, and visual effects. It's designed to be a fast-moving, non-damaging projectile that leaves a trail of cosmetic particles and has a small explosion on death.

## Key Components and Attributes

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`<VelocityComponent>`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="1.7"`: High air friction, suggesting it slows down relatively quickly in the air.
    *   `mass="0.01"`: Very low mass, contributing to its speed and responsiveness.

### Projectile Behavior (`<ProjectileComponent>`)

This is the primary component defining the projectile's unique characteristics.

*   **Movement & Trajectory**:
    *   `lob_min="0.5"`, `lob_max="0.7"`: Controls the arc of the projectile.
    *   `speed_min="350"`, `speed_max="450"`: Defines a high initial speed range.
    *   `direction_random_rad="0.00"`: The projectile travels in a straight line without initial directional randomness.
    *   `friction="1"`: Standard friction.
*   **Impact & Death**:
    *   `on_death_explode="1"`: The projectile explodes when its lifetime ends or it collides.
    *   `on_death_gfx_leave_sprite="0"`: No sprite is left behind upon death.
    *   `on_lifetime_out_explode="1"`: Explodes when lifetime expires.
    *   `on_collision_die="1"`: Dies upon collision with anything.
    *   `lifetime="40"`: The projectile exists for 40 frames.
    *   `lifetime_randomness="7"`: Lifetime can vary by up to 7 frames.
    *   `damage="0.23"`: Deals very minimal damage.
    *   `knockback_force="100.0"`: Applies a moderate knockback force on impact.
*   **Visuals & Effects**:
    *   `muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_air.xml"`: Specifies the muzzle flash particle effect.
    *   `shoot_light_flash_r="128"`, `shoot_light_flash_g="128"`, `shoot_light_flash_b="128"`: Sets the color of the light flash to white.
    *   `shoot_light_flash_radius="48"`: The radius of the light flash.
*   **Explosion Configuration (`<config_explosion>`)**:
    *   `damage="0.0"`: The explosion itself deals no damage.
    *   `camera_shake="0.0"`: No camera shake from the explosion.
    *   `explosion_radius="1"`: A very small explosion radius.
    *   `hole_enabled="1"`: Creates a small hole upon explosion.
    *   `ray_energy="400000"`: High energy for potential environmental interaction.
    *   `physics_throw_enabled="1"`: The explosion can throw physics objects.
    *   `stains_enabled="1"`, `stains_radius="3"`: Leaves a small stain on impact.

### Sprite (`<SpriteComponent>`)

*   `image_file="data/particles/dummy.xml"`: Uses a dummy sprite, indicating the visual representation is likely handled by particle effects.

### Particle Emitters (`<ParticleEmitterComponent>`)

This entity uses two particle emitters to create visual effects.

*   **Emitter 1 (Trail/Spark Effect)**:
    *   `emitted_material_name="spark_white"`: Emits white sparks.
    *   `x_vel_min="0"`, `x_vel_max="40"`: Sparks have horizontal velocity.
    *   `y_vel_min="-10"`, `y_vel_max="10"`: Sparks have vertical velocity.
    *   `gravity.y="0.0"`: Sparks are not affected by gravity.
    *   `lifetime_min="0.2"`, `lifetime_max="1.2"`: Short lifetime for sparks.
    *   `airflow_force="1.5"`, `airflow_time="1.101"`, `airflow_scale="0.05"`: Sparks are influenced by airflow.
    *   `emission_interval_min_frames="2"`, `emission_interval_max_frames="5"`: Emits sparks periodically.
*   **Emitter 2 (Lingering Effect)**:
    *   Similar to Emitter 1 but with longer `lifetime_min="1.2"`, `lifetime_max="3.2"` and less `airflow_force="0.5"`, suggesting a more lingering, less dynamic effect.

### Light Component (`<LightComponent>`)

*   `radius="30"`: Emits a light with a radius of 30 units.

## Summary

The `air_bullet.xml` defines a projectile that is fast, unaffected by gravity, and primarily serves as a visual effect. It deals negligible damage but applies a small knockback and leaves behind cosmetic sparks and a light source. Its explosion is minimal, mainly for environmental interaction and leaving a stain.