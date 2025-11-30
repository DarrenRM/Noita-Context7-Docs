---
title: Machinegun Bullet (Tank Super) Projectile
category: entities
---

# Machinegun Bullet (Tank Super) Projectile

This document details the configuration for a specific projectile entity in Noita, designed to represent a "Machinegun Bullet (Tank Super)". It outlines its physical properties, visual appearance, and associated effects.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This section inherits fundamental projectile behaviors.

*   **`VelocityComponent`**: Defines the projectile's movement characteristics.
    *   `gravity_y="200"`: The projectile is significantly affected by gravity.
    *   `mass="0.08"`: A relatively low mass, contributing to its speed.
    *   `air_friction="0.3"`: Moderate air resistance.

### Projectile Component (`ProjectileComponent`)

This is the primary component defining the projectile's unique attributes and behaviors.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile, suggesting a fairly direct trajectory with minimal lob.
*   **`speed_min="600"`, `speed_max="750"`**: Defines a high initial speed range.
*   **`friction="1"`**: High friction, meaning it slows down quickly.
*   **`direction_random_rad="0.05"`**: Slight randomness in projectile direction.
*   **`on_death_explode="1"`**: The projectile explodes upon death (e.g., collision or lifetime end).
*   **`on_death_gfx_leave_sprite="0"`**: No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode="1"`**: Explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not harm the entity that fired it.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision.
*   **`lifetime="30"`**: The projectile exists for 30 frames.
*   **`lifetime_randomness="7"`**: Lifetime can vary by up to 7 frames.
*   **`damage="0.35"`**: Deals a small amount of direct damage.
*   **`knockback_force="2.6"`**: Applies a moderate knockback force to targets.
*   **`camera_shake_when_shot="0.1"`**: Causes a very minor camera shake when fired.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher.xml"`**: Specifies the muzzle flash particle effect.
*   **`shoot_light_flash_r="120"`, `shoot_light_flash_g="235"`, `shoot_light_flash_b="90"`, `shoot_light_flash_radius="100"`**: Defines a bright green light flash originating from the shooter.

#### `config_explosion`

Details of the explosion effect when the projectile dies.

*   **`damage="0"`**: The explosion itself does not deal direct damage.
*   **`camera_shake="2.0"`**: Causes a significant camera shake upon explosion.
*   **`explosion_radius="6"`**: The radius of the explosion effect.
*   **`explosion_sprite="data/particles/explosion_016_slime.xml"`**: Uses a specific sprite for the explosion visual.
*   **`hole_enabled="1"`**: Creates a hole in terrain.
*   **`ray_energy="300000"`**: High energy for terrain destruction.
*   **`physics_explosion_power.min="0.1"`, `physics_explosion_power.max="0.3"`**: Applies a small physics force to nearby objects.
*   **`shake_vegetation="1"`**: Shakes vegetation within the explosion radius.
*   **`sparks_enabled="1"`, `sparks_count_min="3"`, `sparks_count_max="1"`**: Generates a small number of sparks.
*   **`spark_material="spark_green"`**: The material used for the sparks.
*   **`stains_enabled="1"`, `stains_radius="1"`**: Leaves a stain on surfaces.

### Sprite Component (`SpriteComponent`)

Defines the visual representation of the projectile.

*   **`image_file="data/projectiles_gfx/fireball_smaller_green.xml"`**: Uses a green fireball sprite.
*   **`rect_animation="fireball"`**: Specifies a "fireball" animation.
*   **`additive="1"`**: The sprite uses additive blending, making it appear brighter.

### Audio Component (`AudioComponent`)

Handles sound effects associated with the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing projectile sounds.
*   **`event_root="projectiles/laser"`**: The root event for laser-like projectile sounds.

### Particle Emitters (`ParticleEmitterComponent`)

These components generate visual particle effects.

#### Trail Emitter

*   **`emitted_material_name="spark_yellow"`**: Emits yellow sparks.
*   **`is_trail="1"`**: Creates a trail effect.
*   **`trail_gap="0.6"`**: Spacing between trail particles.
*   **`lifetime_min="0.1"`, `lifetime_max="0.2"`**: Short lifetime for trail particles.
*   **`airflow_force="10.5"`, `airflow_time="1.401"`, `airflow_scale="0.05"`**: Particles are affected by airflow.

#### Secondary Emitter

*   **`emitted_material_name="spark_green"`**: Emits green sparks.
*   **`is_trail="1"`**: Creates a trail effect.
*   **`trail_gap="1.2"`**: Wider spacing for this trail.
*   **`lifetime_min="0.2"`, `lifetime_max="0.6"`**: Longer lifetime for these particles.
*   **`x_vel_min="20"`, `x_vel_max="80"`**: Particles are ejected with significant horizontal velocity.

### Light Component (`LightComponent`)

*   **`radius="30"`**: Emits a light with a radius of 30 units.

### Variable Storage (`VariableStorageComponent`)

*   **`name="projectile_file"`**: Stores the path to this entity's XML file.
*   **`value_string="data/entities/projectiles/machinegun_bullet_tank_super.xml"`**: The value is the path itself.