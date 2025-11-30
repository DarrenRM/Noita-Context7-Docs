---
title: Revenge Tentacle Projectile
category: entities
---

# Revenge Tentacle Projectile

This document describes the `revenge_tentacle_tentacle.xml` entity, which defines a projectile used by the "Revenge Tentacle" perk in Noita. This projectile exhibits homing behavior and utilizes a Verlet physics system for its movement and visual representation.

## Key Components and Attributes

### Base Projectile Configuration

*   **`Base file="data/entities/base_projectile.xml"`**: Inherits fundamental projectile properties.
    *   **`VelocityComponent`**:
        *   `gravity_y="0.0"`: The projectile is not affected by gravity.
        *   `mass="0.07"`: A small mass value.

### Homing Behavior

*   **`HomingComponent`**: Enables the projectile to track targets.
    *   `target_tag="prey"`: Targets entities tagged as "prey".
    *   `homing_targeting_coeff="15"`: Controls the strength of the homing effect.
    *   `detect_distance="300"`: The maximum distance at which the projectile can detect targets.
    *   `homing_velocity_multiplier="1.0"`: Multiplier for the homing velocity.

### Projectile Mechanics

*   **`ProjectileComponent`**: Defines the core projectile behavior.
    *   `projectile_type="VERLET"`: Indicates the use of Verlet physics.
    *   `speed_min="8"`, `speed_max="8"`: The projectile moves at a constant speed of 8.
    *   `die_on_low_velocity="0"`: Does not die if its velocity becomes too low.
    *   `on_death_explode="0"`: Does not explode upon death.
    *   `on_lifetime_out_explode="1"`: Explodes when its lifetime expires.
    *   `on_collision_die="0"`: Does not die upon collision with entities.
    *   `penetrate_entities="1"`: Can pass through multiple entities.
    *   `damage="1.0"`: Base damage dealt by the projectile.
    *   `attach_to_parent_trigger="1"`: Attaches to its parent trigger.
    *   `lifetime="60"`: The projectile exists for 60 frames.
    *   `knockback_force="2.0"`: Applies a knockback force to targets.
    *   **`config_explosion`**: Configuration for the explosion when lifetime expires. Most parameters are set to `0` or disabled, indicating a minimal explosion effect.

### Verlet Weapon Mechanics

*   **`VerletWeaponComponent`**: Manages damage and impulse application related to the Verlet physics.
    *   `fade_duration_frames="20"`: Duration of the fade effect in frames.
    *   `damage_min_step="0.01"`: Minimum damage applied per step.
    *   `damage_max="0.5"`: Maximum damage applied per step.
    *   `damage_coeff="0.0002"`: Coefficient for damage calculation.
    *   `impulse_coeff="0.5"`: Coefficient for impulse application.
    *   `physics_impulse_coeff="4.5"`: Coefficient for physics impulse.

### Verlet Physics Simulation

*   **`VerletPhysicsComponent`**: Governs the Verlet physics simulation for the projectile's segments.
    *   `num_points="12"`: The projectile is composed of 12 points.
    *   `stiffness="0.99"`: High stiffness, making the segments rigid.
    *   `resting_distance="4.0"`: The preferred distance between points.
    *   `pixelate_sprite_transforms="1"`: Pixelates sprite transformations.
    *   `simulate_wind="0"`: Wind simulation is disabled.
    *   `constrain_stretching="0"`: Stretching is not constrained.
    *   `simulate_gravity="0"`: Gravity simulation is disabled for the Verlet points.
    *   `stain_cells_probability="10"`: Probability of leaving stains on cells.

### Visual Components (Tentacle Segments)

*   **`Base file="..."`**: Multiple `Base` tags reference different tentacle segment sprites, creating the visual appearance of the projectile.
    *   `data/entities/projectiles/tentacle/smalltentacle_0.xml`
    *   `data/entities/projectiles/tentacle/smalltentacle_1.xml`
    *   `data/entities/projectiles/tentacle/smalltentacle_1b.xml`
    *   `data/entities/projectiles/tentacle/smalltentacle_2.xml`
    *   `data/entities/projectiles/tentacle/smalltentacle_3.xml`
    *   `data/entities/projectiles/tentacle/smalltentacle_4.xml`

### Audio Configuration

*   **`AudioComponent`**: Defines the sound effects for the projectile.
    *   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
    *   `event_root="projectiles/tentacle_enemy"`: Sets the root event for tentacle enemy projectiles.

### Variable Storage

*   **`VariableStorageComponent`**: Stores a reference to the projectile's own XML file.
    *   `name="projectile_file"`
    *   `value_string="data/entities/misc/perks/revenge_tentacle_tentacle.xml"`