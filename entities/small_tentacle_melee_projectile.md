---
title: Small Tentacle Melee Projectile
category: entities
---

# Small Tentacle Melee Projectile

This document describes the `smalltentacle_melee.xml` entity, which defines a projectile used by a small tentacle enemy in Noita. It's a melee-focused projectile with homing capabilities and a unique Verlet physics simulation.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`gravity_y`**: `0.0` - The projectile is not affected by gravity.
*   **`mass`**: `0.07` - A small mass value.

### Homing Component (`HomingComponent`)

Enables the projectile to track its target.

*   **`target_tag`**: `"prey"` - The projectile will attempt to home in on entities tagged as "prey".
*   **`homing_targeting_coeff`**: `15` - A high coefficient indicating strong homing behavior.
*   **`detect_distance`**: `300` - The maximum distance at which the projectile can detect its target.
*   **`homing_velocity_multiplier`**: `1.0` - The homing mechanism doesn't alter the projectile's base speed.

### Projectile Component (`ProjectileComponent`)

Defines the projectile's behavior and damage.

*   **`projectile_type`**: `"VERLET"` - Utilizes Verlet physics for its movement.
*   **`speed_min` / `speed_max`**: `8` - The projectile travels at a constant speed of 8.
*   **`die_on_low_velocity`**: `0` - The projectile will not die if its velocity drops.
*   **`on_death_explode`**: `0` - Does not explode upon death.
*   **`on_lifetime_out_explode`**: `1` - Explodes when its lifetime expires.
*   **`on_collision_die`**: `0` - Does not die upon colliding with entities.
*   **`penetrate_entities`**: `1` - Can pass through multiple entities.
*   **`damage`**: `0` - Base damage is zero, damage is applied via `VerletWeaponComponent`.
*   **`attach_to_parent_trigger`**: `1` - Can attach to its parent entity.
*   **`lifetime`**: `60` - The projectile exists for 60 frames.
*   **`knockback_force`**: `2.0` - Applies a knockback force of 2.0.

#### Damage By Type (`damage_by_type`)

*   **`melee`**: `1.0` - The projectile deals 1.0 damage of type "melee".

#### Explosion Configuration (`config_explosion`)

This section is largely disabled for this projectile, as its primary damage is not from an explosion.

*   **`damage`**: `0`
*   **`camera_shake`**: `0`
*   **`explosion_radius`**: `0`
*   **`hole_enabled`**: `0`
*   **`particle_effect`**: `0`
*   **`damage_mortals`**: `0`
*   **`physics_explosion_power.max`**: `0`
*   **`physics_throw_enabled`**: `0`

### Verlet Weapon Component (`VerletWeaponComponent`)

This component is crucial for defining the damage and physics interaction of the Verlet projectile.

*   **`fade_duration_frames`**: `20` - The visual fade-out duration.
*   **`damage_min_step`**: `0.01` - Minimum damage dealt per physics step.
*   **`damage_max`**: `0.5` - Maximum damage dealt per physics step.
*   **`damage_coeff`**: `0.0002` - Coefficient for calculating damage over time.
*   **`impulse_coeff`**: `0.5` - Coefficient for impulse applied to entities.
*   **`physics_impulse_coeff`**: `4.5` - Coefficient for physics impulse.

### Verlet Physics Component (`VerletPhysicsComponent`)

This component governs the unique, flexible movement of the projectile.

*   **`num_points`**: `8` - The projectile is simulated as a chain of 8 points.
*   **`stiffness`**: `0.99` - High stiffness, making the chain relatively rigid.
*   **`resting_distance`**: `4.0` - The preferred distance between points.
*   **`pixelate_sprite_transforms`**: `1` - Applies pixelation to sprite transformations.
*   **`simulate_wind`**: `0` - Ignores wind effects.
*   **`constrain_stretching`**: `0` - Allows the chain to stretch.
*   **`simulate_gravity`**: `0` - Ignores gravity.
*   **`stain_cells_probability`**: `10` - Probability of leaving stains.

### Sprite Components (`Base file="..."`)

These components define the visual appearance of the tentacle segments. The projectile is composed of multiple tentacle segments, creating a segmented visual effect.

*   `data/entities/projectiles/tentacle/smalltentacle_0.xml`
*   `data/entities/projectiles/tentacle/smalltentacle_1.xml`
*   `data/entities/projectiles/tentacle/smalltentacle_1b.xml`
*   `data/entities/projectiles/tentacle/smalltentacle_2.xml`
*   `data/entities/projectiles/tentacle/smalltentacle_3.xml`
*   `data/entities/projectiles/tentacle/smalltentacle_4.xml`

### Audio Component (`AudioComponent`)

*   **`file`**: `"data/audio/Desktop/projectiles.bank"` - Specifies the audio bank.
*   **`event_root`**: `"projectiles/tentacle_enemy"` - The root event for tentacle enemy projectile sounds.

### Variable Storage Component (`VariableStorageComponent`)

*   **`name`**: `"projectile_file"`
*   **`value_string`**: `"data/entities/projectiles/smalltentacle_melee.xml"` - Stores the path to this entity's XML file.