---
title: Kantele Projectile (E Note)
category: entities
---

# Kantele Projectile (E Note)

This entity defines the "E" note projectile fired by the Kantele. It's a player projectile with specific visual and auditory components, and it triggers a Lua script for its magical effect.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="8"`: Moderate air resistance.
    *   `mass="0.01"`: Very light mass.

### Projectile Properties (`<ProjectileComponent>`)

Defines the core behavior and characteristics of the projectile.

*   **`lob_min="0.5"`, `lob_max="0.7"`**: Controls the arc of the projectile.
*   **`speed_min="250"`, `speed_max="450"`**: Sets the initial velocity range.
*   **`lifetime="2"`**: The projectile exists for 2 seconds.
*   **`damage="0"`**: This projectile itself does not deal direct damage.
*   **`on_collision_die="0"`**: The projectile does not die upon collision.
*   **`lifetime_randomness="0"`**: Lifetime is fixed.

### Particle Emitters

#### Spark Emitter (`<ParticleEmitterComponent>`)

Generates white sparks as a visual effect.

*   **`emitted_material_name="spark_white"`**: The material used for the sparks.
*   **`count_min="8"`, `count_max="10"`**: Emits 8 to 10 sparks per emission.
*   **`lifetime_min="0.2"`, `lifetime_max="1.2"`**: Sparks last between 0.2 and 1.2 seconds.
*   **`airflow_force="1.5"`, `airflow_time="1.101"`, `airflow_scale="0.05"`**: Influences particle movement with airflow.

#### Sprite Emitter (`<SpriteParticleEmitterComponent>`)

Emits "note" sprites for a distinct visual flair.

*   **`sprite_file="data/particles/note_$[1-4].xml"`**: Uses a set of 4 different note sprites.
*   **`lifetime="1.5"`**: The note sprites last for 1.5 seconds.
*   **`color.r="0.6" color.g="1" color.b="1" color.a="1"`**: Initial color is a bright cyan.
*   **`color_change.a="-1"`**: Alpha (transparency) decreases over time.
*   **`emission_interval_min_frames="4"`, `emission_interval_max_frames="6"`**: Notes are emitted every 4 to 6 frames.
*   **`randomize_rotation.min="-0.3415"`, `randomize_rotation.max="0.3415"`**: Randomizes the initial rotation of the notes.

### Variable Storage (`<VariableStorageComponent>`)

Stores a specific value associated with this projectile.

*   **`name="kantele_note"`**: The variable name.
*   **`value_string="e"`**: The value, indicating this is the "E" note.

### Lua Script (`<LuaComponent>`)

Executes custom logic when the projectile is added.

*   **`script_source_file="data/scripts/magic/kantele.lua"`**: Points to the script that handles the Kantele's magical effects.
*   **`execute_on_added="1"`**: The script runs immediately upon projectile creation.
*   **`remove_after_executed="1"`**: The Lua component is removed after its script has run once.

### Audio (`<AudioComponent>`)

Plays the sound effect for this projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound.
*   **`event_root="player_projectiles/kantele/e"`**: The specific sound event for the Kantele's "E" note.
*   **`set_latest_event_position="1"`**: The sound will originate from the projectile's position.