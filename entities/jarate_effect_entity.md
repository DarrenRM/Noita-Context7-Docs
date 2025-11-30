---
title: Jarate Effect Entity
category: entities
---

# Jarate Effect Entity

This entity defines the properties and behavior of the "Jarate" effect in Noita. It's primarily used to apply a debuff to enemies.

## Core Components

### GameEffectComponent

This component dictates the type and duration of the game effect applied.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `JARATE` | Specifies the type of effect. |
| `frames` | `600` | The duration of the effect in frames (approximately 10 seconds). |

### ParticleEmitterComponent

This component handles the visual representation of the effect, emitting "urine" particles.

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `urine` | The material used for the emitted particles. |
| `gravity.y` | `42` | The gravitational pull affecting the particles. |
| `x_pos_offset_min`, `x_pos_offset_max` | `-4`, `4` | Horizontal offset range for particle emission. |
| `y_pos_offset_min`, `y_pos_offset_max` | `-12`, `0` | Vertical offset range for particle emission. |
| `x_vel_min`, `x_vel_max` | `-11.71`, `11.71` | Minimum and maximum horizontal velocity of particles. |
| `y_vel_min`, `y_vel_max` | `-44.32`, `-19.94` | Minimum and maximum vertical velocity of particles. |
| `count_min`, `count_max` | `1`, `1` | Number of particles emitted per emission event. |
| `lifetime_min`, `lifetime_max` | `0.8`, `2.2` | Minimum and maximum lifetime of individual particles. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1`, `25` | Range for the interval between particle emission events. |
| `is_emitting` | `1` | Enables particle emission. |
| `emit_cosmetic_particles` | `1` | Indicates that these are cosmetic particles. |

## Inheritance

### InheritTransformComponent

This component is present but empty, suggesting it inherits standard transform properties from its parent entity.