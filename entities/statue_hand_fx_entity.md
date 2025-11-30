---
title: Statue Hand FX Entity
category: entities
---

# Statue Hand FX Entity

This entity defines visual effects associated with a statue's hand, primarily particle emissions and sprite rendering. It's designed to add dynamic visual flair to in-game elements.

## Key Components

### ParticleEmitterComponent (Primary)

This component handles the emission of "spark_red" particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material name of the particles to emit (`spark_red`).                   |
| `gravity.y`               | Vertical gravity applied to emitted particles (0.0 means no gravity).       |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime in seconds for each emitted particle.          |
| `count_min`, `count_max`  | Minimum and maximum number of particles emitted per emission event.         |
| `render_on_grid`          | Whether particles should be rendered on the game grid (1 = yes).            |
| `fade_based_on_lifetime`  | Whether particles fade out as their lifetime decreases (1 = yes).           |
| `airflow_force`           | Force applied by airflow to particles.                                      |
| `airflow_time`            | Duration of airflow influence.                                              |
| `airflow_scale`           | Scale of the airflow effect.                                                |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Controls how often particles are emitted (in frames). |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (1 = yes).                               |
| `image_animation_file`    | Path to an image file for animated particle textures.                       |
| `image_animation_speed`   | Speed of the particle image animation.                                      |
| `image_animation_loop`    | Whether the particle image animation should loop (0 = no).                  |
| `is_emitting`             | Whether the emitter is currently active (1 = yes).                          |

### LifetimeComponent

Determines the lifespan of the entity itself.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `lifetime`            | Base lifetime of the entity in seconds (180 seconds).                    |
| `randomize_lifetime`  | Random variation applied to the entity's lifetime (min/max in seconds).  |

### AudioComponent

Defines audio events associated with the entity.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | Path to the sound file (`data/audio/Desktop/projectiles.snd`).           |
| `event_root`| The root event name for audio playback (`player_projectiles/cloud`).     |

### SpriteComponent

Defines the visual sprite for the entity.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `image_file`| Path to the sprite image file (`data/particles/orb_pink_big_out.xml`).   |
| `emissive`  | Whether the sprite should be emissive (glow) (1 = yes).                  |
| `additive`  | Whether the sprite uses additive blending (1 = yes).                     |

### ParticleEmitterComponent (Secondary)

This component handles the emission of "plasma_fading_pink" particles, likely for a secondary effect.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material name of the particles to emit (`plasma_fading_pink`).          |
| `emitter_lifetime_frames` | The lifespan of this specific emitter in frames (80 frames).                |
| `offset.x`, `offset.y`    | Offset from the entity's origin for particle emission.                      |
| `x_pos_offset_min`, `x_pos_offset_max` | Range of horizontal position offset for emitted particles.                |
| `y_pos_offset_min`, `y_pos_offset_max` | Range of vertical position offset for emitted particles.                  |
| `gravity.y`               | Vertical gravity applied to emitted particles (0.0 means no gravity).       |
| `x_vel_min`, `x_vel_max`  | Minimum and maximum horizontal velocity for emitted particles.              |
| `y_vel_min`, `y_vel_max`  | Minimum and maximum vertical velocity for emitted particles.                |
| `count_min`, `count_max`  | Minimum and maximum number of particles emitted per emission event.         |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime in seconds for each emitted particle.          |
| `create_real_particles`   | Whether to create actual game particles (0 = no, cosmetic only).            |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (1 = yes).                               |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Controls how often particles are emitted (in frames). |
| `is_emitting`             | Whether the emitter is currently active (1 = yes).                          |