---
title: Sea Alcohol Projectile
category: entities
---

# Sea Alcohol Projectile

This entity defines a projectile that spawns a "sea" of alcohol. It's primarily used for visual effects and material interaction.

## Key Components

### MaterialSeaSpawnerComponent
This component is responsible for spawning the liquid material.

*   **`size.x`**: Width of the spawned area (300 pixels).
*   **`size.y`**: Height of the spawned area (256 pixels).
*   **`offset.x`**: Horizontal offset for spawning (0).
*   **`offset.y`**: Vertical offset for spawning (158).
*   **`speed`**: Speed at which the material spreads (10).
*   **`noise_threshold`**: Threshold for noise-based spawning (0.0).
*   **`material`**: The material to spawn ("alcohol").

### LifetimeComponent
Determines how long the projectile entity exists.

*   **`lifetime`**: Duration in frames (300 frames).

### ParticleEmitterComponent
Manages the visual particles that make up the "sea".

*   **`emitted_material_name`**: The material of the emitted particles ("alcohol").
*   **`gravity.y`**: Vertical gravity applied to particles (0.0, meaning no gravity).
*   **`lifetime_min`**: Minimum particle lifetime (6 frames).
*   **`lifetime_max`**: Maximum particle lifetime (8 frames).
*   **`count_min`**: Minimum particles emitted per interval (8).
*   **`count_max`**: Maximum particles emitted per interval (8).
*   **`render_on_grid`**: Whether to render particles on the grid (1, enabled).
*   **`fade_based_on_lifetime`**: Whether particles fade as they expire (1, enabled).
*   **`airflow_force`**: Force applied by airflow (0.51).
*   **`airflow_time`**: Duration of airflow effect (1.01).
*   **`airflow_scale`**: Scale of airflow effect (0.05).
*   **`emission_interval_min_frames`**: Minimum frames between emissions (1).
*   **`emission_interval_max_frames`**: Maximum frames between emissions (1).
*   **`emit_cosmetic_particles`**: Whether to emit cosmetic particles (1, enabled).
*   **`image_animation_file`**: Texture file for particle animation ("data/particles/image_emitters/sea_oil.png").
*   **`image_animation_speed`**: Speed of the particle animation (5).
*   **`image_animation_loop`**: Whether the particle animation loops (0, disabled).
*   **`is_emitting`**: Whether the emitter is active (1, enabled).

### MusicEnergyAffectorComponent
This component seems to be related to music or energy effects, though its specific function here is unclear without further context.

*   **`energy_target`**: Target for energy (1).

### AudioComponent
Handles the sound effects associated with the projectile.

*   **`file`**: Audio bank file ("data/audio/Desktop/projectiles.bank").
*   **`event_root`**: Root event name for audio ("player_projectiles/sea_of_oil").
*   **`set_latest_event_position`**: Whether to set the audio event's position (1, enabled).