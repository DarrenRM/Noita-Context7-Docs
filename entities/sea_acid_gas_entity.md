---
title: Sea Acid Gas Entity
category: entities
---

# Sea Acid Gas Entity

This entity defines the behavior and appearance of the "sea of acid gas" effect in Noita. It's primarily used to spawn acid gas and acid particles in a specific area.

## Key Components

### MaterialSeaSpawnerComponent
This component is responsible for spawning the acid gas material.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `size.x`          | Width of the spawning area.                                              |
| `size.y`          | Height of the spawning area.                                             |
| `offset.x`        | X-axis offset for the spawning area.                                     |
| `offset.y`        | Y-axis offset for the spawning area.                                     |
| `speed`           | The speed at which the spawned material moves.                           |
| `noise_threshold` | Controls the density or distribution of the spawned material based on noise. |
| `material`        | The specific material to be spawned (e.g., "acid_gas").                  |

### LifetimeComponent
Determines how long the entity persists.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The duration in frames the entity exists. |

### ParticleEmitterComponent
Manages the emission of acid particles.

| Attribute                   | Description                                                                                                |
| :-------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`     | The material name of the particles to be emitted (e.g., "acid").                                           |
| `gravity.y`                 | The gravitational pull on the emitted particles along the Y-axis.                                          |
| `lifetime_min`              | Minimum lifetime of individual particles.                                                                  |
| `lifetime_max`              | Maximum lifetime of individual particles.                                                                  |
| `count_min`                 | Minimum number of particles emitted per emission cycle.                                                    |
| `count_max`                 | Maximum number of particles emitted per emission cycle.                                                    |
| `render_on_grid`            | Whether particles should be rendered on the game grid.                                                     |
| `fade_based_on_lifetime`    | If true, particles fade out as their lifetime decreases.                                                   |
| `airflow_force`             | The force applied to particles by airflow.                                                                 |
| `airflow_time`              | The duration for which airflow affects particles.                                                          |
| `airflow_scale`             | The scaling factor for airflow effects.                                                                    |
| `image_animation_file`      | Path to the image file used for particle animation.                                                        |
| `image_animation_speed`     | Speed of the particle image animation.                                                                     |
| `is_emitting`               | Whether the particle emitter is currently active.                                                          |

### MusicEnergyAffectorComponent
This component influences the game's music energy.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `energy_target` | The target energy level for the music.    |

### AudioComponent
Handles the sound effects associated with the entity.

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `file`         | Path to the audio bank file.                                             |
| `event_root`   | The root event name for the audio, specifying the sound to play.         |
| `set_latest_event_position` | If true, the sound's position will be updated to the entity's position. |