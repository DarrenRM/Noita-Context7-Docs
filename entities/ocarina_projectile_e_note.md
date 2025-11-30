---
title: Ocarina Projectile (E Note)
category: entities
---

# Ocarina Projectile (E Note)

This entity defines the "E" note projectile fired by the Ocarina. It's a player projectile with specific velocity, particle effects, and a Lua script for its behavior.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="8"`: Moderate air resistance.
    *   `mass="0.01"`: Very light projectile.

### Projectile Properties (`<ProjectileComponent>`)

This is the core component defining the projectile's behavior.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.5"`, `lob_max="0.7"`**: Controls the arc of the projectile.
*   **`speed_min="250"`, `speed_max="450"`**: Defines the projectile's speed range.
*   **`lifetime="2"`**: The projectile exists for 2 seconds.
*   **`damage="0"`**: This projectile itself does not deal direct damage.
*   **`on_collision_die="0"`**: The projectile does not die upon collision.
*   **`explosion_dont_damage_shooter="0"`**: If it were to explode, it could damage the shooter.
*   **`lifetime_randomness="0"`**: The lifetime is fixed.

### Particle Emitter (`<ParticleEmitterComponent>`)

Generates white sparks as a visual effect.

*   **`emitted_material_name="spark_white"`**: The material used for the emitted particles.
*   **`count_min="8"`, `count_max="10"`**: Emits 8 to 10 particles per emission.
*   **`lifetime_min="0.2"`, `lifetime_max="1.2"`**: Particles last between 0.2 and 1.2 seconds.
*   **`is_trail="0"`**: These are not trail particles.
*   **`airflow_force="1.5"`, `airflow_time="1.101"`, `airflow_scale="0.05"`**: Particles are affected by airflow.
*   **`create_real_particles="0"`**: These are cosmetic particles, not physics-simulated ones.

### Sprite Particle Emitter (`<SpriteParticleEmitterComponent>`)

Emits sprite-based particles resembling musical notes.

*   **`sprite_file="data/particles/note_$[1-4].xml"`**: Uses note sprites for visual flair.
*   **`lifetime="1.5"`**: These note sprites last for 1.5 seconds.
*   **`color.r="0.6" color.g="1" color.b="1" color.a="1"`**: The notes are a bright cyan color.
*   **`color_change.a="-1"`**: The alpha (transparency) of the notes decreases over their lifetime.
*   **`emission_interval_min_frames="4"`, `emission_interval_max_frames="6"`**: Notes are emitted every 4 to 6 frames.
*   **`count_min="1"`, `count_max="1"`**: One note sprite is emitted at a time.
*   **`randomize_rotation`**, **`randomize_angular_velocity`**, **`randomize_velocity`**: Adds slight variations to the notes' movement and rotation.

### Variable Storage (`<VariableStorageComponent>`)

Stores information about the specific note.

*   **`name="ocarina_note"`**: The variable name.
*   **`value_string="e"`**: The value, indicating this is the "E" note.

### Lua Script (`<LuaComponent>`)

Executes the Ocarina's logic.

*   **`script_source_file="data/scripts/magic/ocarina.lua"`**: Links to the main Ocarina script.
*   **`execute_on_added="1"`**: The script runs as soon as the entity is added.
*   **`remove_after_executed="1"`**: The Lua component is removed after execution.

### Audio (`<AudioComponent>`)

Plays the sound effect for the "E" note.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound.
*   **`event_root="player_projectiles/ocarina/e"`**: The specific sound event for this note.
*   **`set_latest_event_position="1"`**: The sound will originate from the projectile's position.