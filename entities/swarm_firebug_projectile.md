---
title: Swarm Firebug Projectile
category: entities
---

# Swarm Firebug Projectile

This document details the `swarm_firebug.xml` entity, representing a projectile used in Noita. It's designed to be a homing, bouncing projectile that leaves a trail of fire.

## Core Components

### Base Projectile (`BaseComponent`)

*   **`gravity_y`**: `50` - Applies a downward gravitational pull.
*   **`air_friction`**: `2` - Resistance to movement in the air.
*   **`mass`**: `0.03` - The projectile's mass, affecting its interaction with physics.

### Homing Behavior (`HomingComponent`)

*   **`target_who_shot`**: `1` - The projectile will attempt to home in on its owner.
*   **`homing_targeting_coeff`**: `10.0` - Strength of the homing behavior.
*   **`detect_distance`**: `300` - The range within which the projectile can detect its target.

### Projectile Mechanics (`ProjectileComponent`)

*   **`lob_min` / `lob_max`**: `0.5` / `0.7` - Controls the arc of the projectile's trajectory.
*   **`speed_min` / `speed_max`**: `50` / `150` - The range of initial speeds.
*   **`direction_random_rad`**: `0.8` - Introduces randomness to the projectile's initial direction.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion will not harm the entity that fired it.
*   **`die_on_liquid_collision`**: `1` - The projectile is destroyed upon colliding with liquids.
*   **`lifetime`**: `850` - The maximum duration the projectile exists in frames.
*   **`damage`**: `0.0` - Base damage of the projectile itself (before elemental application).
*   **`bounces_left`**: `10` - The maximum number of bounces allowed.
*   **`bounce_energy`**: `1.0` - How much velocity is retained after a bounce.
*   **`knockback_force`**: `0.4` - The force applied to knock back entities on collision.
*   **`physics_impulse_coeff`**: `1200` - Affects how much physics impulse is applied on collision.
*   **`damage_every_x_frames`**: `20` - The interval (in frames) at which damage is applied.

#### Damage Types (`damage_by_type`)

*   **`fire`**: `0.15` - Applies a small amount of fire damage.

#### Explosion Configuration (`config_explosion`)

*   **`load_this_entity`**: `data/entities/particles/swarm_poof.xml` - The entity spawned upon explosion.
*   **`hole_enabled`**: `1` - Creates a hole in terrain upon explosion.
*   **`sparks_count_min` / `sparks_count_max`**: `4` - The range for the number of sparks generated.
*   **`spark_material`**: `plasma_fading_pink` - The material used for sparks.

### Visuals (`SpriteComponent`)

*   **`image_file`**: `data/projectiles_gfx/swarm_firebug.xml` - Specifies the sprite animation file.

### Audio (`AudioComponent`, `AudioLoopComponent`)

*   **`AudioComponent`**: Plays a sound event `player_projectiles/bullet_smg` on creation.
*   **`AudioLoopComponent`**: Plays a looping movement sound `player_projectiles/fly/movement_loop`.

### Scripting (`LuaComponent`)

*   **`script_source_file`**: `data/scripts/projectiles/swarm_fly.lua` - The Lua script controlling projectile behavior.
*   **`execute_every_n_frame`**: `6` - The script executes every 6 frames.

### Damage Model (`DamageModelComponent`)

*   **`hp`**: `0.5` - The projectile's health.
*   **`wet_status_effect_damage`**: `0.3` - Damage taken when wet.
*   **`materials_that_damage`**: `acid,water,poison,blood_cold,blood_cold_vapour,water_ice` - Materials that damage the projectile.
*   **`materials_how_much_damage`**: `0.004,0.05,0.001,0.08,0.07,0.01` - The corresponding damage values for the materials listed above.

### Hitbox (`HitboxComponent`)

*   **`aabb_min_x` / `aabb_max_x`**: `-2` / `2` - Defines the horizontal bounds of the hitbox.
*   **`aabb_min_y` / `aabb_max_y`**: `-2` / `2` - Defines the vertical bounds of the hitbox.

### Particle Emitters (`ParticleEmitterComponent`)

There are two `ParticleEmitterComponent` instances, both emitting `fire` material:

1.  **Trail Emitter**:
    *   **`offset.x`**: `-1`
    *   **`is_trail`**: `1`
    *   **`trail_gap`**: `1.0`
    *   **`lifetime_min` / `lifetime_max`**: `0.6` / `1.8`
    *   **`create_real_particles`**: `1`
    *   **`delay_frames`**: `2`

2.  **Burst Emitter**:
    *   **`offset.x`**: `-1`
    *   **`x_pos_offset_min` / `y_pos_offset_min`**: `-4` / `-4`
    *   **`x_pos_offset_max` / `y_pos_offset_max`**: `-2` / `4`
    *   **`lifetime_min` / `lifetime_max`**: `1.1` / `2.8`
    *   **`create_real_particles`**: `1`
    *   **`delay_frames`**: `2`

### Variable Storage (`VariableStorageComponent`)

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/swarm_firebug.xml` - Stores the entity's own file path.