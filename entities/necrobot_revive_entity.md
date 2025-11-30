---
title: Necrobot Revive Entity
category: entities
---

# Necrobot Revive Entity

This entity defines the visual and functional components for the Necrobot's revive effect. It's primarily used to indicate when a Necrobot is attempting to revive a fallen enemy.

## Key Components

### `VariableStorageComponent`

This component stores a string value that likely points to the entity that the Necrobot is attempting to revive.

*   **`_tags`**: `necrobot_entity_file` - A tag indicating the purpose of this entity file.
*   **`name`**: `necrobot_entity_file` - The name of the variable storage.
*   **`value_string`**: `data/entities/animals/zombie.xml` - The path to the entity being revived.

### `SpriteComponent`

Defines the visual representation of the revive effect.

*   **`image_file`**: `data/particles/skullface.xml` - The texture used for the revive effect.
*   **`offset_x`, `offset_y`**: `0` - No offset from the entity's origin.
*   **`additive`**: `1` - Enables additive blending for the sprite.
*   **`emissive`**: `1` - Makes the sprite emissive, meaning it emits light.

### `LuaComponent`

Handles the logic for the revive effect, specifically its termination.

*   **`script_source_file`**: `data/scripts/status_effects/necrobot_end.lua` - The script responsible for managing the end of the revive effect.
*   **`execute_every_n_frame`**: `120` - The script will execute every 120 frames.

### `ParticleEmitterComponent`

Generates cosmetic particles to enhance the visual feedback of the revive action.

*   **`emitted_material_name`**: `spark_green` - The material used for the emitted particles.
*   **`offset.x`, `offset.y`**: `0` - Particles are emitted from the entity's origin.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-12` to `12` - Horizontal spread of particle emission.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `-12` to `12` - Vertical spread of particle emission.
*   **`gravity.y`**: `0` - Particles are not affected by gravity.
*   **`x_vel_min`, `x_vel_max`**: `-2` to `2` - Minimum and maximum horizontal velocity of particles.
*   **`y_vel_min`, `y_vel_max`**: `-2` to `2` - Minimum and maximum vertical velocity of particles.
*   **`count_min`, `count_max`**: `1` to `2` - Number of particles emitted per emission.
*   **`lifetime_min`, `lifetime_max`**: `0.8` to `2.0` - Duration particles exist.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `2` to `5` - Frame interval between particle emissions.
*   **`is_emitting`**: `1` - The particle emitter is active.
*   **`emit_cosmetic_particles`**: `1` - Only cosmetic particles are emitted.

### `AudioComponent`

Plays a sound effect associated with the revive action.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_root`**: `projectiles/revive` - The specific sound event to trigger.