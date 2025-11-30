---
title: Curse Rain Effect
category: entities
---

# Curse Rain Effect

This entity defines the visual and auditory components of the "Curse Rain" effect in Noita. It primarily utilizes particle emitters to simulate falling fire and smoke, accompanied by sound effects.

## Key Components

### `GameEffectComponent`

This component applies a game effect to the entity.

| Attribute      | Value        | Description                                     |
|----------------|--------------|-------------------------------------------------|
| `effect`       | `INTERNAL_FIRE` | The internal game effect to apply.              |
| `frames`       | `100`        | Duration of the effect in frames.               |
| `disable_movement` | `0`          | Whether movement is disabled (0 means not disabled). |

### `ParticleEmitterComponent` (Fire)

This component configures the emission of fire particles.

| Attribute               | Value   | Description                                                              |
|-------------------------|---------|--------------------------------------------------------------------------|
| `emitted_material_name` | `fire`  | The material name of the particles to emit.                              |
| `custom_style`          | `FIRE`  | A custom style tag for the particles.                                    |
| `count_min`             | `5`     | Minimum number of particles emitted per emission.                        |
| `count_max`             | `5`     | Maximum number of particles emitted per emission.                        |
| `offset.x`              | `-1`    | X-axis offset for the emitter's position.                                |
| `offset.y`              | `-5`    | Y-axis offset for the emitter's position.                                |
| `x_pos_offset_min`      | `-5`    | Minimum X-axis positional variation for emitted particles.               |
| `x_pos_offset_max`      | `5`     | Maximum X-axis positional variation for emitted particles.               |
| `y_pos_offset_min`      | `-4`    | Minimum Y-axis positional variation for emitted particles.               |
| `y_pos_offset_max`      | `4`     | Maximum Y-axis positional variation for emitted particles.               |
| `lifetime_min`          | `1.1`   | Minimum lifetime of emitted particles in seconds.                        |
| `lifetime_max`          | `2.8`   | Maximum lifetime of emitted particles in seconds.                        |
| `create_real_particles` | `1`     | Whether to create actual game particles (1 means yes).                   |
| `emit_cosmetic_particles`| `0`     | Whether to emit cosmetic particles (0 means no).                         |
| `emission_interval_min_frames` | `1` | Minimum frames between particle emissions.                               |
| `emission_interval_max_frames` | `1` | Maximum frames between particle emissions.                               |
| `delay_frames`          | `2`     | Delay in frames before the emitter starts.                               |
| `is_emitting`           | `1`     | Whether the emitter is currently active (1 means yes).                   |

### `ParticleEmitterComponent` (Smoke)

This component configures the emission of smoke particles. It is similar to the fire emitter but is initially inactive.

| Attribute               | Value   | Description                                                              |
|-------------------------|---------|--------------------------------------------------------------------------|
| `_tags`                 | `smoke` | A tag associated with this emitter.                                      |
| `emitted_material_name` | `smoke` | The material name of the particles to emit.                              |
| `count_min`             | `1`     | Minimum number of particles emitted per emission.                        |
| `count_max`             | `5`     | Maximum number of particles emitted per emission.                        |
| `offset.x`              | `-1`    | X-axis offset for the emitter's position.                                |
| `offset.y`              | `-5`    | Y-axis offset for the emitter's position.                                |
| `x_pos_offset_min`      | `-2`    | Minimum X-axis positional variation for emitted particles.               |
| `x_pos_offset_max`      | `2`     | Maximum X-axis positional variation for emitted particles.               |
| `y_pos_offset_min`      | `-4`    | Minimum Y-axis positional variation for emitted particles.               |
| `y_pos_offset_max`      | `4`     | Maximum Y-axis positional variation for emitted particles.               |
| `lifetime_min`          | `1.1`   | Minimum lifetime of emitted particles in seconds.                        |
| `lifetime_max`          | `2.8`   | Maximum lifetime of emitted particles in seconds.                        |
| `create_real_particles` | `1`     | Whether to create actual game particles (1 means yes).                   |
| `emit_cosmetic_particles`| `0`     | Whether to emit cosmetic particles (0 means no).                         |
| `emission_interval_min_frames` | `1` | Minimum frames between particle emissions.                               |
| `emission_interval_max_frames` | `1` | Maximum frames between particle emissions.                               |
| `delay_frames`          | `2`     | Delay in frames before the emitter starts.                               |
| `is_emitting`           | `0`     | Whether the emitter is currently active (0 means no).                    |

### `AudioComponent`

This component plays a one-time sound effect when the entity is activated.

| Attribute              | Value                     | Description                                       |
|------------------------|---------------------------|---------------------------------------------------|
| `file`                 | `data/audio/Desktop/misc.bank` | The audio bank file containing the sound event.   |
| `event_root`           | `game_effect/on_fire`     | The root event name for the sound.                |
| `set_latest_event_position` | `1`                   | Whether to set the sound's position to the entity. |

### `AudioLoopComponent`

This component plays a looping sound effect while the entity is active.

| Attribute   | Value                     | Description                                       |
|-------------|---------------------------|---------------------------------------------------|
| `file`      | `data/audio/Desktop/misc.bank` | The audio bank file containing the sound event.   |
| `event_name`| `game_effect/on_fire/burning` | The name of the looping sound event.              |
| `auto_play` | `1`                       | Whether the sound should start automatically (1 means yes). |