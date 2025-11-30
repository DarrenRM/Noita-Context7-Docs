---
title: Sun Spot 1 Process Entity
category: entities
---

# Sun Spot 1 Process Entity

This entity defines the visual and functional aspects of the "Sun Spot 1" building process in Noita. It handles particle effects, script execution for completion, and audio cues.

## Key Components

### ParticleEmitterComponent

This component manages the visual buildup effect for the Sun Spot 1.

| Attribute                 | Value                                     | Description                                                                 |
| :------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark`                                   | The material of the particles being emitted.                                |
| `lifetime_min`            | `0.8`                                     | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`            | `5.5`                                     | Maximum lifetime of emitted particles in seconds.                           |
| `count_min`               | `20`                                      | Minimum number of particles emitted per emission.                           |
| `count_max`               | `40`                                      | Maximum number of particles emitted per emission.                           |
| `fade_based_on_lifetime`  | `1`                                       | Particles fade out as their lifetime decreases.                             |
| `airflow_force`           | `1.1`                                     | Force applied to particles by airflow.                                      |
| `emission_interval_min_frames` | `1`                                       | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `1`                                       | Maximum frames between particle emissions.                                  |
| `image_animation_file`    | `data/particles/image_emitters/circle_reverse_64.png` | The sprite sheet used for animating the emitted particles.                  |
| `image_animation_speed`   | `3.5`                                     | Speed of the particle image animation.                                      |
| `render_ultrabright`      | `1`                                       | Particles are rendered with ultrabrightness.                                |
| `is_emitting`             | `1`                                       | Enables particle emission.                                                  |

### LuaComponent

This component links to a Lua script that handles the completion logic for the Sun Spot 1.

| Attribute          | Value                                     | Description                                                                 |
| :----------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `script_source_file` | `data/scripts/buildings/sun/spot_1_finish.lua` | The path to the Lua script that executes when the building process is complete. |
| `execute_every_n_frame` | `80`                                      | The script will execute every 80 frames.                                    |

### LifetimeComponent

This component defines how long the Sun Spot 1 process entity will exist.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `81`  | The entity will exist for 81 seconds.     |

### AudioComponent

This component plays a sound effect associated with the building process.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.snd`| The sound file to be played.                                                |
| `event_root`| `player_projectiles/crumbling_earth`| The specific audio event within the sound file to trigger.                  |