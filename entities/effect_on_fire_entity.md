---
title: Effect On Fire Entity
category: entities
---

# Effect On Fire Entity

This entity defines the visual and auditory effects associated with an entity being set on fire in Noita. It primarily uses particle emitters to create fire and smoke visuals, and audio components for burning sounds.

## Key Components

### `GameEffectComponent`

This component signifies that the entity applies a specific game effect.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `effect`         | The type of game effect. Set to `"ON_FIRE"` for this entity.             |
| `frames`         | The duration (in frames) for which the effect is active.                 |
| `disable_movement` | If set to `1`, this effect will prevent the entity from moving.          |

### `ParticleEmitterComponent` (Fire)

This component is responsible for emitting fire particles.

| Attribute                 | Description                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to emit. Set to `"fire"`.                                                    |
| `custom_style`            | A specific style for the emitted particles. Set to `"FIRE"`.                                               |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission cycle.                                    |
| `offset.x`, `offset.y`    | The base offset from the entity's position where particles are emitted.                                    |
| `x_pos_offset_min/max`    | The range for random horizontal offset of emitted particles.                                               |
| `y_pos_offset_min/max`    | The range for random vertical offset of emitted particles.                                                 |
| `x_vel_min/max`, `y_vel_min/max` | The velocity range for emitted particles. Set to `0` for static fire.                                      |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifespan of individual particles.                                                  |
| `create_real_particles`   | If `1`, creates actual game particles.                                                                     |
| `emit_cosmetic_particles` | If `1`, emits cosmetic particles (less performance intensive). Set to `0` for real fire.                   |
| `emission_interval_min/max_frames` | The interval (in frames) between particle emissions. Set to `1` for continuous emission.                 |
| `delay_frames`            | A delay in frames before particle emission begins.                                                         |
| `is_emitting`             | Whether the emitter is currently active. Set to `1` for the fire emitter.                                  |

### `ParticleEmitterComponent` (Smoke)

This component is responsible for emitting smoke particles. It shares many attributes with the fire emitter but is configured for smoke.

| Attribute                 | Description                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `_tags`                   | Tags associated with this emitter. Set to `"smoke"`.                                                       |
| `emitted_material_name`   | The material of the particles to emit. Set to `"smoke"`.                                                   |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission cycle.                                    |
| `offset.x`, `offset.y`    | The base offset from the entity's position where particles are emitted.                                    |
| `x_pos_offset_min/max`    | The range for random horizontal offset of emitted particles.                                               |
| `y_pos_offset_min/max`    | The range for random vertical offset of emitted particles.                                                 |
| `x_vel_min/max`, `y_vel_min/max` | The velocity range for emitted particles. Set to `0` for static smoke.                                     |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifespan of individual particles.                                                  |
| `create_real_particles`   | If `1`, creates actual game particles.                                                                     |
| `emit_cosmetic_particles` | If `1`, emits cosmetic particles. Set to `0` for real smoke.                                               |
| `emission_interval_min/max_frames` | The interval (in frames) between particle emissions. Set to `1` for continuous emission.                 |
| `delay_frames`            | A delay in frames before particle emission begins.                                                         |
| `is_emitting`             | Whether the emitter is currently active. Set to `0` by default, meaning smoke is not emitted unless triggered. |

### `AudioComponent`

This component plays a one-time audio event when the entity is created or activated.

| Attribute              | Description                                                              |
| :--------------------- | :----------------------------------------------------------------------- |
| `file`                 | The audio bank file containing the sound events.                         |
| `event_root`           | The root path for the audio event. Set to `"game_effect/on_fire"`.       |
| `set_latest_event_position` | If `1`, the sound will be positioned at the entity's location.          |

### `AudioLoopComponent`

This component plays a looping audio event while the entity is active.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | The audio bank file containing the sound events.                         |
| `event_name`| The name of the looping audio event. Set to `"game_effect/on_fire/burning"`. |
| `auto_play` | If `1`, the sound will start playing automatically when the entity is active. |