---
title: Enlightened Laser Darkbeam Projectile
category: entities
---

# Enlightened Laser Darkbeam Projectile

This document details the configuration for the "enlightened_laser_darkbeam.xml" projectile entity in Noita, designed for AI-assisted modding.

## Core Components

This projectile is primarily defined by its `ProjectileComponent` and `Base` projectile properties.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This section inherits fundamental projectile behaviors.

*   **`VelocityComponent`**:
    *   `air_friction`: `-50` (High air friction, suggesting it's not significantly affected by air resistance once launched).
    *   `gravity_y`: `0` (No vertical gravity applied to the projectile itself).
    *   `mass`: `0.04` (Lightweight projectile).

### Projectile Component (`ProjectileComponent`)

This is the main component defining the projectile's unique characteristics and behaviors.

*   **Movement & Trajectory**:
    *   `lob_min`, `lob_max`: `0.8` to `1.0` (Controls the arc of the projectile, suggesting a mostly straight trajectory with minimal lob).
    *   `speed_min`, `speed_max`: `40` (Constant speed).
*   **Lifetime & Destruction**:
    *   `lifetime`: `180` (Duration the projectile exists before expiring).
    *   `on_death_explode`: `1` (Explodes upon death).
    *   `on_lifetime_out_explode`: `1` (Explodes when its lifetime expires).
    *   `on_collision_die`: `1` (Dies upon colliding with something).
    *   `explosion_dont_damage_shooter`: `1` (The explosion from this projectile will not harm the entity that fired it).
*   **Damage & Impact**:
    *   `damage`: `1` (Base damage dealt by the projectile).
    *   `knockback_force`: `1.5` (Force applied to entities it hits).
    *   `penetrate_entities`: `0` (Does not penetrate other entities).
*   **Visuals & Effects**:
    *   `shoot_light_flash_radius`, `shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`: Defines a light flash effect upon shooting (radius 15, color purple/pink).
    *   `hit_particle_force_multiplier`: `0.25` (Affects particle force on impact).
    *   `ragdoll_fx_on_collision`: `BLOOD_SPRAY` (Applies a blood spray effect on collision).
*   **Explosion Configuration (`config_explosion`)**:
    *   `camera_shake`: `4.5` (Significant camera shake on explosion).
    *   `explosion_radius`: `3` (Radius of the explosion).
    *   `explosion_sprite`: `data/particles/explosion_016_plasma_pink.xml` (Visual sprite for the explosion).
    *   `create_cell_material`: `spark_purple_bright` (Material of cells created by the explosion).
    *   `create_cell_probability`: `15` (Chance of creating cells).
    *   `hole_enabled`: `1` (Creates a hole on impact).
    *   `ray_energy`: `100000` (High energy for potential ray interactions).
    *   `damage`: `0.22` (Damage dealt by the explosion itself).
    *   `physics_explosion_power.min`, `physics_explosion_power.max`: `0.2` to `0.35` (Force of the physics-based explosion).
    *   `stains_enabled`: `1` (Leaves stains on impact).
    *   `stains_radius`: `4` (Radius of the stains).

## Particle Emitters

The projectile utilizes two `ParticleEmitterComponent`s for visual effects.

### Solid Particle Line

*   `emitted_material_name`: `spark_purple_bright`
*   `is_trail`: `1` (Emits a continuous trail).
*   `trail_gap`: `0.5` (Small gap between trail particles).
*   `lifetime_min`, `lifetime_max`: `0.4` (Short lifetime for trail particles).
*   `emit_cosmetic_particles`: `1` (Emits cosmetic particles).

### Secondary Sprinkles

*   `emitted_material_name`: `spark_purple_bright`
*   `is_trail`: `1` (Emits a trail).
*   `trail_gap`: `5` (Larger gap for sparser sprinkles).
*   `lifetime_min`, `lifetime_max`: `0.2` to `0.8` (Variable lifetime for sprinkle particles).
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `1` to `2` (Emits particles frequently).

## Other Components

*   **`LifetimeComponent` (Secondary)**:
    *   `lifetime`: `250` (An additional, longer lifetime component, likely a failsafe if the primary one is bypassed or for specific activation scenarios).
*   **`VariableStorageComponent`**:
    *   `name`: `projectile_file`
    *   `value_string`: `data/entities/projectiles/enlightened_laser_darkbeam.xml` (Stores the path to this entity's XML file, useful for scripting).

---