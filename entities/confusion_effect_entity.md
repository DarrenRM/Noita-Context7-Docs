---
title: Confusion Effect Entity
category: entities
---

# Confusion Effect Entity

This entity defines the visual and functional aspects of the "Confusion" status effect in Noita. When applied, it causes visual distortions and potentially affects player input.

## Key Components

### GameEffectComponent

This component is responsible for applying the actual game effect.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `CONFUSION` | Specifies the type of game effect to apply. |
| `frames` | `1000` | The duration of the effect in frames (approximately 16.67 seconds). |

### SpriteParticleEmitterComponent

This component generates visual particles to represent the confusion effect.

| Attribute | Value | Description |
|---|---|---|
| `sprite_file` | `data/particles/shine_confusion.xml` | The particle sprite definition to use. |
| `delay` | `0` | No initial delay before particle emission. |
| `lifetime` | `0` | Particles have no inherent lifetime and are managed by the emitter. |
| `color.r`, `color.g`, `color.b`, `color.a` | `1` | Initial color of the particles (white). |
| `gravity.y` | `10` | Particles are affected by a slight downward gravity. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1`, `2` | Particles are emitted every 1 to 2 frames. |
| `count_min`, `count_max` | `1`, `4` | Emits between 1 and 4 particles per emission interval. |
| `randomize_rotation.min`, `randomize_rotation.max` | `-3.1415`, `3.1415` | Particles are emitted with random rotations. |
| `randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y` | `-4`, `4`, `-4`, `4` | Particles are emitted within a small radius around the entity's position. |