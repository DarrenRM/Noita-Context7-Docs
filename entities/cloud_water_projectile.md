---
title: Cloud Water Projectile
category: entities
---

# Cloud Water Projectile

This entity defines the behavior and appearance of the "Cloud Water" projectile in Noita. It's primarily a visual effect that emits water particles and has a long lifetime.

## Key Components

### Entity Name & Tags
- **`name`**: `$projectile_default` (This is a base projectile, likely intended to be inherited and modified for specific projectile types. In this case, it's configured for cloud water.)
- **`tags`**: `projectile_player` (Indicates this projectile is fired by the player.)

### Base Projectile Inheritance
- **`Base file="data/entities/base_projectile.xml"`**: Inherits core projectile properties.
    - **`VelocityComponent`**:
        - `gravity_y="0"`: The projectile is not affected by gravity.
        - `air_friction="-0.2"`: Minimal air friction.

### Projectile Component
- **`ProjectileComponent`**: Configures the projectile's movement and interaction.
    - `lob_min="0.8"`, `lob_max="1.0"`: Controls the lobbing behavior (though speed is zero, so this might be less impactful).
    - `speed_min="0"`, `speed_max="0"`: The projectile has no initial speed.
    - `direction_random_rad="0.00"`: No random deviation in direction.
    - `on_death_explode="0"`: Does not explode on death.
    - `on_collision_die="0"`: Does not die on collision.
    - `lifetime="999"`: Extremely long lifetime, making it persistent.
    - `damage="0"`: Deals no damage.

### Particle Emitters
This entity utilizes multiple `ParticleEmitterComponent`s to create the visual effect of a cloud.

1.  **Water Emitter**:
    - `emitted_material_name="water"`: Emits water particles.
    - `count_min="1"`, `count_max="10"`: Emits a small burst of water.
    - `emission_interval_min_frames="3"`, `emission_interval_max_frames="3"`: Emits water particles frequently.
    - `image_animation_file="data/particles/image_emitters/cloud_bottom.png"`: Uses a specific sprite for the water emission.
    - `create_real_particles="1"`: Creates actual water particles that interact with the world.

2.  **Cosmetic Steam Emitter (First Instance)**:
    - `emitted_material_name="steam"`: Emits steam particles.
    - `count_min="1"`, `count_max="1"`: Emits a single steam particle at a time.
    - `lifetime_min="0.2"`, `lifetime_max="0.5"`: Short-lived steam particles.
    - `image_animation_file="data/particles/image_emitters/cloud.png"`: Uses a cloud sprite.
    - `emit_cosmetic_particles="1"`: These are purely visual.
    - `create_real_particles="0"`: Does not create real, interactive particles.
    - `is_emitting="0"`: This emitter is initially off, likely controlled by script.

3.  **Real Steam Emitter (Second Instance)**:
    - `emitted_material_name="steam"`: Emits steam particles.
    - `count_min="1"`, `count_max="1"`: Emits a single steam particle.
    - `lifetime_min="0.2"`, `lifetime_max="0.5"`: Short-lived steam particles.
    - `emission_interval_min_frames="1"`, `emission_interval_max_frames="10"`: Emits steam particles with some variation.
    - `image_animation_file="data/particles/image_emitters/cloud.png"`: Uses a cloud sprite.
    - `emit_cosmetic_particles="0"`: Creates real steam particles.
    - `create_real_particles="1"`: Creates actual steam particles.
    - `is_emitting="0"`: This emitter is initially off, likely controlled by script.

4.  **Cosmetic Blue Spark Emitter (First Instance)**:
    - `emitted_material_name="spark_blue"`: Emits blue spark particles.
    - `count_min="1"`, `count_max="1"`: Emits a single spark.
    - `lifetime_min="0.5"`, `lifetime_max="0.8"`: Short-lived sparks.
    - `airflow_force="0.015"`, `airflow_scale="0.01"`, `airflow_time="0.1"`: Subtle airflow influence.
    - `image_animation_file="data/particles/image_emitters/cloud_outline.png"`: Uses a cloud outline sprite.
    - `emit_cosmetic_particles="1"`: Purely visual.
    - `create_real_particles="0"`: Does not create real particles.

5.  **Cosmetic Blue Spark Emitter (Second Instance)**:
    - `emitted_material_name="spark_blue"`: Emits blue spark particles.
    - `count_min="1"`, `count_max="1"`: Emits a single spark.
    - `lifetime_min="2.5"`, `lifetime_max="3.8"`: Longer-lived sparks.
    - `airflow_force="0.15"`, `airflow_scale="0.1"`, `airflow_time="0.1"`: More pronounced airflow influence.
    - `emission_interval_min_frames="55"`, `emission_interval_max_frames="60"`: Infrequent emission.
    - `image_animation_file="data/particles/image_emitters/cloud_outline.png"`: Uses a cloud outline sprite.
    - `emit_cosmetic_particles="1"`: Purely visual.
    - `create_real_particles="0"`: Does not create real particles.

### Lifetime Component
- **`LifetimeComponent`**:
    - `lifetime="600"`: The entity persists for a long duration.

### Audio Component
- **`AudioComponent`**:
    - `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
    - `event_root="player_projectiles/cloud"`: Links to the "cloud" sound event for player projectiles.

### Lua Component
- **`LuaComponent`**:
    - `script_source_file="data/scripts/projectiles/cloud_position.lua"`: Executes a Lua script to manage the entity's behavior, likely controlling particle emission and movement.
    - `execute_times="1"`: The script is executed once.