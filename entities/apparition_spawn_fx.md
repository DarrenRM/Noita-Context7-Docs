---
title: Apparition Spawn FX
category: entities
---

# Apparition Spawn FX

This entity defines the visual and auditory effects associated with the spawning of the "Apparition" boss in Noita. It primarily uses a `ParticleEmitterComponent` to create visual effects and an `AudioLoopComponent` for sound.

## Key Components

### ParticleEmitterComponent

This component is responsible for generating the visual particles that signify the Apparition's appearance.

*   **`emitted_material_name`**: `spark_blue` - The type of material used for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`lifetime_min` / `lifetime_max`**: `1` / `2` - The duration each particle exists in seconds.
*   **`count_min` / `count_max`**: `2` / `2` - The number of particles emitted per emission.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`collide_with_grid`**: `0` - Particles do not collide with the grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`airflow_force`**: `0.251` - The force applied to particles by airflow.
*   **`airflow_scale`**: `0.05` - The scaling factor for airflow effects.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted every frame.
*   **`emit_cosmetic_particles`**: `1` - Emits particles that are purely cosmetic.
*   **`image_animation_file`**: `data/entities/animals/boss_sky/apparition_spawn_fx_emitter.png` - The sprite sheet used for particle animation.
*   **`image_animation_speed`**: `1` - The speed of the particle animation.
*   **`image_animation_loop`**: `0` - The particle animation does not loop.
*   **`is_emitting`**: `1` - The particle emitter is active.

### LifetimeComponent

Determines how long this entity exists.

*   **`lifetime`**: `160` - The entity will exist for 160 frames (approximately 2.67 seconds).

### LuaComponent

This component executes a Lua script, likely for managing the spawning logic or other behaviors related to the Apparition.

*   **`script_source_file`**: `data/entities/animals/boss_sky/boss_sky.lua` - The path to the Lua script.
*   **`execute_on_removed`**: `1` - The script will execute when the entity is removed.

### AudioLoopComponent

Handles the looping sound effect associated with the spawn.

*   **`file`**: `data/audio/Desktop/misc.bank` - The audio bank containing the sound event.
*   **`event_name`**: `misc/runestone_loop` - The name of the sound event to play.
*   **`auto_play`**: `1` - The sound effect will start playing automatically.

## Entity Tags

*   `miniboss`: Indicates this entity is related to a miniboss.
*   `music_energy_50`: Suggests a connection to a specific music energy level.