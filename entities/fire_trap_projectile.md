---
title: Fire Trap Projectile
category: entities
---

# Fire Trap Projectile

This document details the configuration of the `fire_trap.xml` entity, which defines a player-owned projectile with fire-based properties.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile behaviors.

*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`air_friction="1.7"`**: A moderate amount of air friction is applied.
*   **`mass="0.01"`**: The projectile has a very low mass.

### Projectile Component (`<ProjectileComponent>`)

This is the primary component defining the projectile's unique characteristics.

*   **`lob_min="0.5"`, `lob_max="0.7"`**: Controls the arc of the projectile.
*   **`speed_min="250"`, `speed_max="250"`**: Sets a fixed projectile speed.
*   **`lifetime="20"`**: The projectile exists for 20 frames.
*   **`lifetime_randomness="7"`**: Adds up to 7 frames of randomness to the projectile's lifetime.
*   **`damage="0.0"`**: The projectile itself deals no direct damage.
*   **`penetrate_entities="1"`**: The projectile can pass through multiple entities.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision.
*   **`explosion_dont_damage_shooter="1"`**: If an explosion occurs on death, it will not harm the shooter.
*   **`damage_by_type`**:
    *   **`fire="0.53"`**: Applies 0.53 damage of the "fire" type.

### Particle Emitter Components

These components define the visual effects associated with the projectile.

#### Spark Emitter (`<ParticleEmitterComponent emit_material_name="spark">`)

*   **`count_min="3"`, `count_max="4"`**: Emits 3 to 4 sparks per emission.
*   **`lifetime_min="0.2"`, `lifetime_max="1.2"`**: Sparks last between 0.2 and 1.2 frames.
*   **`x_vel_max="40"`, `y_vel_min="-10"`, `y_vel_max="10"`**: Defines the initial velocity range for sparks.
*   **`airflow_force="1.5"`, `airflow_time="1.101"`, `airflow_scale="0.05"`**: Controls how sparks interact with airflow.

#### Fire Emitter (`<ParticleEmitterComponent emit_material_name="fire">`)

*   **`count_min="4"`, `count_max="8"`**: Emits 4 to 8 fire particles per emission.
*   **`lifetime_min="0.1"`, `lifetime_max="0.3"`**: Fire particles have a very short lifespan.
*   **`x_vel_min="-10"`, `x_vel_max="10"`, `y_vel_min="-10"`, `y_vel_max="10"`**: Defines the initial velocity range for fire particles.
*   **`create_real_particles="1"`**: These are actual game particles, not just cosmetic.

### Light Component (`<LightComponent>`)

*   **`radius="30"`**: Emits a light source with a radius of 30 units.

### Magic Convert Material Component (`<MagicConvertMaterialComponent>`)

*   **`fan_the_flames="10"`**: This likely influences how the projectile interacts with or spreads fire.
*   **`radius="10"`**: The area of effect for material conversion.

### Audio Component (`<AudioComponent>`)

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank.
*   **`event_root="projectiles/trap_fire"`**: The root event for the projectile's sound effects.

### Variable Storage Component (`<VariableStorageComponent>`)

*   **`name="projectile_file"`**: Stores the path to this projectile's XML file.
*   **`value_string="data/entities/projectiles/fire_trap.xml"`**: The value is the file path itself.