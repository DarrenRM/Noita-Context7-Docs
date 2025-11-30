---
title: Projectile - Grenade Leader
category: entities
---

# Projectile - Grenade Leader

This document details the configuration for the "Grenade Leader" projectile entity in Noita, primarily focusing on its behavior, appearance, and effects.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `mass`: `0.07` - Defines the projectile's mass.
    *   `air_friction`: `0.0` - No air friction applied.

### Projectile Component (`<ProjectileComponent>`)

This is the primary component defining the projectile's unique characteristics.

*   **Behavior**:
    *   `_enabled`: `1` - Enables the projectile component.
    *   `lob_min`, `lob_max`: `0.2`, `0.5` - Controls the minimum and maximum lob angle when fired.
    *   `speed_min`, `speed_max`: `80`, `90` - Sets the projectile's initial speed range.
    *   `friction`: `0.6` - Applies friction to the projectile's movement.
    *   `direction_random_rad`: `0.05` - Introduces a small random deviation in the projectile's direction.
    *   `on_death_explode`: `1` - The projectile explodes upon death.
    *   `on_lifetime_out_explode`: `1` - The projectile explodes when its lifetime expires.
    *   `on_collision_die`: `1` - The projectile dies upon collision.
    *   `lifetime`: `500` - The base lifetime of the projectile in frames.
    *   `lifetime_randomness`: `7` - Adds randomness to the projectile's lifetime.
    *   `bounces_left`: `4` - The number of bounces the projectile can perform before dying.
    *   `knockback_force`: `2.0` - The force applied to entities hit by the projectile.

*   **Damage & Effects**:
    *   `damage`: `0.5` - The base damage dealt by the projectile.
    *   `explosion_dont_damage_shooter`: `0` - The explosion can damage the shooter.
    *   `ragdoll_force_multiplier`: `0.04` - Multiplier for ragdoll force applied on impact.
    *   `hit_particle_force_multiplier`: `5.5` - Multiplier for particle force on hit.
    *   `camera_shake_when_shot`: `5.0` - Camera shake applied when the projectile is shot.
    *   `shoot_light_flash_radius`: `80` - Radius of the light flash when shot.
    *   `muzzle_flash_file`: `data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml` - Specifies the muzzle flash particle effect.

*   **Explosion Configuration (`<config_explosion>`)**:
    *   `camera_shake`: `10` - Intensity of camera shake during explosion.
    *   `explosion_radius`: `10` - The radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_016.xml` - The sprite used for the explosion effect.
    *   `load_this_entity`: `data/entities/particles/particle_explosion/main_gunpowder_tiny.xml` - The entity loaded upon explosion.
    *   `ray_energy`: `25000` - Energy of the explosion's damaging rays.
    *   `damage`: `0.5` - Damage dealt by the explosion.
    *   `physics_explosion_power.min`, `physics_explosion_power.max`: `0.15`, `0.35` - Minimum and maximum physics force of the explosion.
    *   `shake_vegetation`: `1` - Whether the explosion shakes vegetation.
    *   `sparks_count_min`, `sparks_count_max`: `4`, `10` - Range for the number of sparks created.
    *   `stains_radius`: `12` - Radius of stains left by the explosion.
    *   `audio_event_name`: `explosions/grenade_small` - The audio event triggered by the explosion.

### Sprite Component (`<SpriteComponent>`)

Defines the visual representation of the projectile.

*   `image_file`: `data/projectiles_gfx/grenade_scavenger.xml` - The sprite sheet used for the projectile.
*   `alpha`: `1` - Full opacity.

### Particle Emitter Component (`<ParticleEmitterComponent>`)

Responsible for emitting particles.

*   `emitted_material_name`: `smoke` - The material of the emitted particles.
*   `count_min`, `count_max`: `1`, `1` - Emits a single particle per emission.
*   `lifetime_min`, `lifetime_max`: `0.1`, `0.3` - Lifetime of emitted particles.
*   `is_emitting`: `1` - The emitter is active.

### Light Component (`<LightComponent>`)

Adds a light source to the projectile.

*   `radius`: `40` - The radius of the light.

### Audio Component (`<AudioComponent>`)

Handles sound effects.

*   `file`: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   `event_root`: `projectiles/bullet_launcher` - The root event for projectile sounds.

### Variable Storage Component (`<VariableStorageComponent>`)

Stores custom variables.

*   `name`: `projectile_file`
*   `value_string`: `data/entities/projectiles/grenade_leader.xml` - Stores the path to this entity's XML file.