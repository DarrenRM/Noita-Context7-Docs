---
title: Effect Protection All (Short Duration)
category: entities
---

# Effect Protection All (Short Duration)

This entity defines a short-duration buff that grants the player protection against all damage types. It's primarily used for visual effects and applying the protection status.

## Key Components

### `GameEffectComponent`

This component applies the actual game effect.

| Attribute | Description |
|---|---|
| `effect` | Specifies the type of effect. `PROTECTION_ALL` grants immunity to all damage. |
| `frames` | The duration of the effect in frames. `100` frames is a short duration. |
| `_tags` | Internal tags for identifying the effect. |

### `SpriteParticleEmitterComponent`

This component handles the visual particle effects associated with the protection buff.

| Attribute | Description |
|---|---|
| `sprite_file` | Path to the particle sprite definition (`data/particles/protection_all.xml`). |
| `delay` | Delay before the emitter starts. `0` means immediate. |
| `lifetime` | Lifetime of the emitter. `0` means it runs indefinitely as long as the entity exists. |
| `color.r`, `color.g`, `color.b`, `color.a` | Initial color of the particles. `1, 1, 1, 1` is white. |
| `velocity.y` | Initial vertical velocity of particles. `-20` means upward. |
| `gravity.y` | Gravity applied to particles. `10` pulls them down. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Controls the rate at which particles are emitted. |
| `count_min`, `count_max` | Number of particles emitted per interval. |
| `randomize_position` | Range for randomizing particle spawn positions around the entity. |
| `additive` | `1` means particles use additive blending, making them brighter. |
| `emissive` | `1` means particles emit light. |

## Usage

This entity is typically spawned by other game mechanics or spells to grant temporary, universal damage resistance to the player. The `frames` attribute in `GameEffectComponent` dictates how long this protection lasts.