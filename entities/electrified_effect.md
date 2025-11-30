---
title: Electrified Effect
category: entities
---

# Electrified Effect

This entity defines the visual and particle effects associated with being electrified in Noita. It primarily uses particle emitters to create visual feedback for this status.

## Key Components

### SpriteParticleEmitterComponent

This component controls the emission of a specific sprite as a particle effect.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `sprite_file`             | Path to the sprite file used for particles (`data/particles/spark_electric.xml`). |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | Maximum frames between particle emissions.                                  |
| `count_min`               | Minimum number of particles emitted per emission.                           |
| `count_max`               | Maximum number of particles emitted per emission.                           |
| `randomize_rotation.min`  | Minimum random rotation applied to emitted particles.                       |
| `randomize_rotation.max`  | Maximum random rotation applied to emitted particles.                       |
| `randomize_position.min_x`| Minimum X-axis offset for particle position.                                |
| `randomize_position.max_x`| Maximum X-axis offset for particle position.                                |
| `randomize_position.min_y`| Minimum Y-axis offset for particle position.                                |
| `randomize_position.max_y`| Maximum Y-axis offset for particle position.                                |
| `randomize_velocity.min_x`| Minimum X-axis velocity for emitted particles.                              |
| `randomize_velocity.max_x`| Maximum X-axis velocity for emitted particles.                              |
| `randomize_velocity.min_y`| Minimum Y-axis velocity for emitted particles.                              |
| `randomize_velocity.max_y`| Maximum Y-axis velocity for emitted particles.                              |

### ParticleEmitterComponent

This component defines the emission of a specific material as particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The name of the material to be emitted (`spark_blue`).                      |
| `x_pos_offset_min`        | Minimum X-axis offset for particle emission.                                |
| `x_pos_offset_max`        | Maximum X-axis offset for particle emission.                                |
| `y_pos_offset_min`        | Minimum Y-axis offset for particle emission.                                |
| `y_pos_offset_max`        | Maximum Y-axis offset for particle emission.                                |
| `x_vel_min`               | Minimum X-axis velocity for emitted particles.                              |
| `x_vel_max`               | Maximum X-axis velocity for emitted particles.                              |
| `y_vel_min`               | Minimum Y-axis velocity for emitted particles.                              |
| `y_vel_max`               | Maximum Y-axis velocity for emitted particles.                              |
| `count_min`               | Minimum number of particles emitted per emission.                           |
| `count_max`               | Maximum number of particles emitted per emission.                           |
| `lifetime_min`            | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`            | Maximum lifetime of emitted particles in seconds.                           |
| `emission_interval_min_frames` | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | Maximum frames between particle emissions.                                  |
| `is_emitting`             | Whether the emitter is active (`1` for true).                               |

### LifetimeComponent

This component defines the duration for which the entity (and its effects) will persist.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total lifetime of the entity in seconds (`200`). |