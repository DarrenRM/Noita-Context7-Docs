---
title: Wizard Cave Gate Entity
category: entities
---

# Wizard Cave Gate Entity

This document details the `wizardcave_gate.xml` entity, which represents a decorative and functional gate found in wizard caves. It primarily focuses on its visual effects, lighting, and scripting for interactive behavior.

## Key Components

### Particle Emitters

The gate utilizes two `ParticleEmitterComponent` instances to create visual effects.

#### Stationary Particles

*   **`emitted_material_name`**: `spark_red` - The material used for the emitted particles.
*   **`offset.x`**: `-5`, **`offset.y`**: `5` - Position offset for particle emission.
*   **`lifetime_min`**: `2`, **`lifetime_max`**: `5` - Duration of particles in seconds.
*   **`count_min`**: `1`, **`count_max`**: `1` - Number of particles emitted per interval.
*   **`emit_cosmetic_particles`**: `1` - Ensures particles are rendered.
*   **`cosmetic_force_create`**: `1` - Forces the creation of cosmetic particles.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`collide_with_grid`**: `0` - Particles do not collide with the grid.
*   **`image_animation_file`**: `data/particles/image_emitters/wizardcave_gate_ornaments.png` - Specifies the sprite sheet for particle animation.

#### Radial Movement Particles

*   **`emitted_material_name`**: `spark_red` - The material used for the emitted particles.
*   **`offset.x`**: `-5`, **`offset.y`**: `5` - Position offset for particle emission.
*   **`lifetime_min`**: `2`, **`lifetime_max`**: `12` - Duration of particles in seconds.
*   **`count_min`**: `1`, **`count_max`**: `1` - Number of particles emitted per interval.
*   **`emit_cosmetic_particles`**: `1` - Ensures particles are rendered.
*   **`cosmetic_force_create`**: `0` - Cosmetic particles are not forced.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`collide_with_grid`**: `1` - Particles collide with the grid.
*   **`velocity_always_away_from_center`**: `25` - Particles are propelled radially outwards.
*   **`airflow_force`**: `0.164` - Affects particle movement with airflow.
*   **`image_animation_file`**: `data/particles/image_emitters/wizardcave_gate_ornaments.png` - Specifies the sprite sheet for particle animation.

### Light Component

*   **`radius`**: `200` - The radius of the light emitted by the gate.
*   **`r`**: `255`, **`g`**: `25`, **`b`**: `20` - The RGB color of the light (a reddish hue).

### Variable Storage Component

*   **`name`**: `egg_count` - A variable to store an integer value, likely for tracking something related to the gate's functionality.
*   **`value_int`**: `0` - The initial integer value of the `egg_count`.

### Lua Component

*   **`script_source_file`**: `data/scripts/buildings/wizardcave_gate.lua` - Links to the Lua script that controls the gate's behavior and logic.
*   **`execute_every_n_frame`**: `1` - The script executes every frame, indicating continuous processing.

### Audio Loop Component

*   **`file`**: `data/audio/Desktop/misc.bank` - The audio bank containing the sound event.
*   **`event_name`**: `misc/wizardcave_gate_loop` - The name of the looping audio event.
*   **`auto_play`**: `1` - The audio loop starts automatically when the entity is spawned.