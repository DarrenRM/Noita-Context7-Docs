---
title: Tongue Projectile
category: entities
---

# Tongue Projectile

This document details the configuration of the "tongue" projectile entity in Noita, focusing on its behavior and physics.

## Core Components

The tongue projectile is a complex entity built upon several base components, defining its movement, interaction, and visual properties.

### Base Projectile (`base_projectile.xml`)

This component defines fundamental projectile properties.

*   **`gravity_y`**: `0.0` - The projectile is not affected by gravity.
*   **`mass`**: `0.08` - A small mass value, influencing its interaction with physics.

### Projectile Component (`ProjectileComponent`)

This is the primary component for defining projectile behavior.

*   **`projectile_type`**: `VERLET` - Indicates the use of Verlet physics for simulation.
*   **`speed_min` / `speed_max`**: `8` - The projectile travels at a constant speed of 8.
*   **`die_on_low_velocity`**: `0` - The projectile does not die when its velocity becomes low.
*   **`on_death_explode`**: `0` - No explosion occurs upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No sprite is left behind upon death.
*   **`on_lifetime_out_explode`**: `0` - No explosion occurs when the lifetime expires.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision.
*   **`penetrate_entities`**: `1` - The projectile can pass through entities.
*   **`damage`**: `0` - The projectile itself deals no direct damage.
*   **`attach_to_parent_trigger`**: `1` - Allows the projectile to attach to a parent trigger.
*   **`lifetime`**: `35` - The projectile exists for 35 frames.
*   **`knockback_force`**: `1.0` - Applies a knockback force of 1.0.

#### Damage by Type

*   **`melee`**: `0.4` - Deals 0.4 damage when originating from a melee source.

#### Configuration Explosion (`config_explosion`)

This section defines explosion properties, which are largely disabled for this projectile.

*   **`never_cache`**: `1` - The explosion configuration is never cached.
*   **`damage`**: `0` - No damage from explosion.
*   **`camera_shake`**: `0` - No camera shake.
*   **`explosion_radius`**: `0` - No explosion radius.
*   **`hole_enabled`**: `0` - No holes are created.
*   **`particle_effect`**: `0` - No particle effects.
*   **`damage_mortals`**: `0` - Does not damage mortals.
*   **`physics_throw_enabled`**: `0` - Physics-based throwing is disabled.

### Verlet Weapon Component (`VerletWeaponComponent`)

This component governs the specific behavior of the tongue using Verlet physics.

*   **`fade_duration_frames`**: `20` - The visual fade duration of the tongue.
*   **`damage_min_step`**: `0.01` - Minimum damage dealt per step of the Verlet simulation.
*   **`damage_max`**: `0.5` - Maximum damage dealt by the tongue.
*   **`damage_coeff`**: `0.0002` - Coefficient for calculating damage.
*   **`impulse_coeff`**: `0.5` - Coefficient for impulse applied.
*   **`physics_impulse_coeff`**: `3.5` - Coefficient for physics impulse.

### Verlet Physics Component (`VerletPhysicsComponent`)

Defines the parameters for the Verlet physics simulation.

*   **`num_points`**: `13` - The number of points used to simulate the tongue's structure.
*   **`stiffness`**: `0.99` - Controls how rigid the tongue is.
*   **`resting_distance`**: `4.0` - The preferred distance between simulation points.
*   **`pixelate_sprite_transforms`**: `1` - Sprite transformations are pixelated.
*   **`simulate_wind`**: `0` - Wind simulation is disabled.
*   **`constrain_stretching`**: `0` - Stretching is not constrained.
*   **`simulate_gravity`**: `0` - Gravity simulation is disabled for the Verlet points.

## Visual and Audio Components

### Base Files (`Base file="..."`)

The tongue's visual appearance and structure are assembled from multiple base entity files, likely defining segments or visual elements of the tongue.

*   `data/entities/projectiles/tentacle/tongue_0.xml`
*   `data/entities/projectiles/tentacle/tongue_1.xml`
*   `data/entities/projectiles/tentacle/tongue_2.xml` (appears twice)
*   `data/entities/projectiles/tentacle/tongue_3.xml` (appears five times)
*   `data/entities/projectiles/tentacle/tentacle_4.xml`

### Audio Component (`AudioComponent`)

Defines the sound effects associated with the tongue projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sounds.
*   **`event_root`**: `projectiles/tongue` - The root event for tongue-related audio.

## Variable Storage

### Variable Storage Component (`VariableStorageComponent`)

Stores a variable for potential use by other systems.

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/tongue.xml` - The path to this projectile's definition file.