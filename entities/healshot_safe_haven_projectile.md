---
title: Healshot Safe Haven Projectile
category: entities
---

# Healshot Safe Haven Projectile

This document describes the `healshot_safe_haven.xml` entity, which defines a projectile that heals entities it hits.

## Core Functionality

The `healshot_safe_haven.xml` entity represents a projectile with the primary function of healing. It inherits base projectile properties and adds specific behaviors for healing and its visual/audio presentation.

## Key Components and Attributes

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `mass="0.04"`: Defines the projectile's mass.
    *   `air_friction="0"`: No air friction is applied.

### Starting Velocity (`SetStartVelocityComponent`)

*   **`randomize_angle.min="-3.141"` / `randomize_angle.max="3.141"`**: The projectile's initial direction can be randomized across a full circle.
*   **`randomize_speed.min="20"` / `randomize_speed.max="100"`**: The projectile's initial speed is randomized within this range.

### Projectile Behavior (`ProjectileComponent`)

*   **`_enabled="1"`**: This component is active.
*   **`lob_min="0.8"` / `lob_max="1.1"`**: Controls the arc of the projectile.
*   **`friendly_fire="1"`**: The projectile can affect friendly entities.
*   **`speed_min="100"` / `speed_max="250"`**: The projectile's speed range.
*   **`friction="0"`**: No friction is applied to the projectile.
*   **`direction_random_rad="0.003"`**: Small randomization in projectile direction.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not damage the entity that fired it.
*   **`on_collision_die="1"`**: The projectile dies upon collision.
*   **`lifetime="260"`**: The base lifetime of the projectile in frames.
*   **`lifetime_randomness="100"`**: Randomness added to the projectile's lifetime.
*   **`bounce_always="1"`**: The projectile will always bounce.
*   **`bounces_left="50"`**: The maximum number of bounces allowed.
*   **`bounce_energy="0.99"`**: The energy retained after each bounce.
*   **`damage="0"`**: The projectile itself deals no damage.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_large.xml"`**: Specifies the muzzle flash particle effect.

#### Healing (`damage_by_type`)

*   **`healing="-0.2"`**: This is the key attribute for healing. A negative value in `damage_by_type` signifies healing.

#### Explosion Configuration (`config_explosion`)

*   **`damage="0"`**: The explosion deals no damage.
*   **`camera_shake="0"`**: No camera shake is triggered by the explosion.
*   **`explosion_radius="1"`**: The radius of the explosion effect.
*   **`explosion_sprite="data/particles/explosion_016_plasma_green.xml"`**: The visual sprite for the explosion.
*   **`physics_throw_enabled="1"`**: The explosion can cause physics-based throws.
*   **`shake_vegetation="1"`**: The explosion can shake vegetation.

### Visuals (`SpriteComponent`)

*   **`image_file="data/projectiles_gfx/grenade_green.xml"`**: The visual sprite for the projectile.
*   **`emissive="1"` / `additive="1"`**: The sprite is emissive and uses additive blending for a glowing effect.

### Particle Emitter (`SpriteParticleEmitterComponent`)

*   **`sprite_file="data/particles/heal.xml"`**: Specifies the particle effect used for healing.
*   **`emission_interval_min_frames="6"` / `emission_interval_max_frames="10"`**: Controls the frequency of particle emissions.
*   **`count_min="1"` / `count_max="1"`**: The number of particles emitted per interval.
*   **`randomize_position`**: Particles are emitted with slight positional randomization.
*   **`randomize_velocity`**: Particles are emitted with slight velocity randomization.

### Audio (`AudioComponent`)

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing projectile sounds.
*   **`event_root="projectiles/bullet_heal"`**: The specific audio event for this projectile.

### Variable Storage (`VariableStorageComponent`)

*   **`name="projectile_file"`**: Stores the path to this projectile's XML file.
*   **`value_string="data/entities/projectiles/healshot_safe_haven.xml"`**: The value is the file path itself.