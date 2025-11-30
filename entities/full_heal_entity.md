---
title: Full Heal Entity
category: entities
---

# Full Heal Entity

This entity represents a "full heal" effect, likely used in Noita for restoring health or providing a temporary invulnerability. It utilizes particle effects for visual feedback, a Lua script for its core functionality, and an audio component for sound.

## Key Components

### ParticleEmitterComponent

This component handles the visual effects associated with the full heal.

*   **`_tags="buildup_particles"`**: Indicates these particles are part of a buildup or activation sequence.
*   **`emitted_material_name="spark_green"`**: Specifies the material used for the emitted particles, in this case, green sparks.
*   **`lifetime_min="0.8"`, `lifetime_max="5.5"`**: Controls the duration each individual particle exists.
*   **`count_min="5"`, `count_max="15"`**: Determines the number of particles emitted per burst.
*   **`render_on_grid="1"`**: Ensures the particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles will fade out as their lifetime expires.
*   **`airflow_force="1.1"`, `airflow_time="1.01"`, `airflow_scale="0.05"`**: These parameters influence how particles interact with airflow in the game.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`**: Particles are emitted continuously with no delay between frames.
*   **`emit_cosmetic_particles="1"`**: Allows for the emission of cosmetic particles.
*   **`image_animation_file="data/particles/image_emitters/circle_reverse_64.png"`**: Specifies the sprite sheet for particle animation.
*   **`image_animation_speed="2.5"`**: Controls the speed of the particle animation.
*   **`image_animation_loop="0"`**: The particle animation does not loop.
*   **`is_emitting="1"`**: The particle emitter is active.

### LuaComponent

This component executes a Lua script to define the entity's behavior.

*   **`script_source_file="data/scripts/buildings/fullheal.lua"`**: Points to the external Lua script responsible for the full heal's logic.
*   **`execute_every_n_frame="102"`**: The script's logic is executed every 102 frames.

### LifetimeComponent

This component defines the overall duration of the entity.

*   **`lifetime="103"`**: The entity will exist for 103 frames before being removed.

### AudioComponent

This component handles the sound effects associated with the entity.

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank containing the sound event.
*   **`event_root="projectiles/bullet_heal_robot"`**: Identifies the specific sound event to be played.