---
title: Acid Shot (Slow) Projectile
category: entities
---

# Acid Shot (Slow) Projectile

This document details the configuration for the "Acid Shot (Slow)" projectile entity in Noita, primarily used by boss meat enemies.

## Core Components

### Entity Name
*   `$projectile_default`: This is a generic projectile entity name, indicating it inherits base projectile properties.

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)
*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `mass="0.07"`: Defines the projectile's mass.

### Projectile Component (`<ProjectileComponent>`)
This component governs the projectile's behavior and effects.

*   **Behavior**:
    *   `_enabled="1"`: The component is active.
    *   `speed_min="90"`, `speed_max="90"`: The projectile travels at a constant speed of 90 units.
    *   `die_on_low_velocity="0"`: The projectile does not die if its velocity drops too low.
    *   `on_death_explode="1"`: The projectile explodes upon death.
    *   `on_death_gfx_leave_sprite="0"`: No sprite is left behind when the projectile dies.
    *   `explosion_dont_damage_shooter="1"`: The explosion does not harm the entity that fired it.
    *   `on_lifetime_out_explode="1"`: The projectile explodes when its lifetime expires.
    *   `on_collision_die="1"`: The projectile dies upon collision.
*   **Damage & Knockback**:
    *   `damage="0.4"`: The projectile deals 0.4 damage on impact.
    *   `lifetime="100"`: The projectile exists for 100 frames before expiring.
    *   `knockback_force="1.0"`: Applies a knockback force of 1.0.

#### Explosion Configuration (`<config_explosion>`)
Details the effects when the projectile explodes.

*   **General**:
    *   `never_cache="1"`: This explosion effect is not cached.
    *   `damage="0.3"`: The explosion deals 0.3 damage.
    *   `camera_shake="3.5"`: Causes significant camera shake.
    *   `explosion_radius="9"`: The explosion affects an area with a radius of 9.
    *   `hole_enabled="1"`: Creates a hole in the environment.
    *   `hole_image="data/temp/explosion_hole.png"`: Uses a specific image for the hole.
    *   `damage_mortals="1"`: The explosion damages mortal entities.
*   **Physics & Particles**:
    *   `physics_explosion_power.min="0.4"`, `physics_explosion_power.max="0.6"`: Controls the physics force of the explosion.
    *   `physics_throw_enabled="1"`: Enables physics-based throwing of debris.
    *   `sparks_count_max="20"`, `sparks_count_min="7"`: Generates a variable number of sparks.
    *   `stains_enabled="1"`, `stains_radius="9"`: Creates stains with a radius of 9.
*   **Material Creation**:
    *   `create_cell_material="pus"`: Creates "pus" material upon explosion.
    *   `create_cell_probability="40"`: There's a 40% chance to create the "pus" material.

### Sprite Component (`<SpriteComponent>`)
Defines the visual appearance of the projectile.

*   `image_file="data/projectiles_gfx/slimeball_red.xml"`: Uses a red slimeball graphic.
*   `alpha="1"`: Fully opaque.

### Particle Emitter Component (`<ParticleEmitterComponent>`)
Responsible for emitting cosmetic particles.

*   `emitted_material_name="acid"`: Emits particles of the "acid" material.
*   **Emission Properties**:
    *   `count_min="1"`, `count_max="2"`: Emits 1-2 particles per emission.
    *   `lifetime_min="0.1"`, `lifetime_max="0.3"`: Particles last for 0.1 to 0.3 seconds.
    *   `emission_interval_min_frames="5"`, `emission_interval_max_frames="8"`: Emits particles every 5-8 frames.
    *   `is_emitting="1"`: The emitter is active.
*   **Velocity**:
    *   `x_vel_min="-50"`, `x_vel_max="50"`
    *   `y_vel_min="-50"`, `y_vel_max="50"`: Particles are emitted with a random velocity within this range.

### Audio Component (`<AudioComponent>`)
Handles sound effects for the projectile.

*   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
*   `event_root="projectiles/acid"`: Sets the root event for acid projectile sounds.

### Variable Storage Component (`<VariableStorageComponent>`)
Stores custom variables for the entity.

*   `name="projectile_file"`: The name of the variable.
*   `value_string="data/entities/animals/boss_meat/acidshot_slow.xml"`: Stores the path to this entity's XML file, likely for referencing by other systems.