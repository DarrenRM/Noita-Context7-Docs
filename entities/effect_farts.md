---
title: Effect Farts
category: entities
---

# Effect Farts

This entity defines the visual and functional aspects of the "Farts" game effect in Noita. It's primarily used to create a puff of gas particles.

## Key Components

### GameEffectComponent

This component assigns the entity to the "FARTS" game effect and sets its duration.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `FARTS` | Identifies this as the Farts effect. |
| `frames` | `600` | The duration of the effect in frames (approximately 10 seconds). |

### ParticleEmitterComponent

This component is responsible for generating the gas particles that constitute the fart effect.

| Attribute | Value | Description |
|---|---|---|
| `_tags` | `fart` | A tag for identifying these particles. |
| `emitted_material_name` | `acid_gas` | The material of the particles emitted (acid gas). |
| `offset.x` | `-1` | Horizontal offset for particle emission. |
| `offset.y` | `-4` | Vertical offset for particle emission. |
| `x_pos_offset_min` | `-1` | Minimum horizontal position variation for emitted particles. |
| `x_pos_offset_max` | `1` | Maximum horizontal position variation for emitted particles. |
| `y_pos_offset_max` | `0` | Maximum vertical position variation for emitted particles. |
| `x_vel_min` | `-7` | Minimum horizontal velocity for emitted particles. |
| `x_vel_max` | `7` | Maximum horizontal velocity for emitted particles. |
| `y_vel_min` | `80` | Minimum vertical velocity for emitted particles. |
| `y_vel_max` | `180` | Maximum vertical velocity for emitted particles. |
| `count_min` | `3` | Minimum number of particles emitted per burst. |
| `count_max` | `7` | Maximum number of particles emitted per burst. |
| `lifetime_min` | `0.1` | Minimum lifetime of emitted particles in seconds. |
| `lifetime_max` | `0.2` | Maximum lifetime of emitted particles in seconds. |
| `create_real_particles` | `1` | Indicates that actual game particles should be created. |
| `emit_cosmetic_particles` | `1` | Indicates that cosmetic particles should also be emitted. |
| `emission_interval_min_frames` | `0` | Minimum frames between particle emissions. |
| `emission_interval_max_frames` | `1` | Maximum frames between particle emissions. |
| `is_emitting` | `0` | This particle emitter is not set to emit continuously by default; it's likely triggered by the `GameEffectComponent`. |