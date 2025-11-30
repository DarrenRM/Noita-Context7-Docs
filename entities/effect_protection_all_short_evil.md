---
title: Effect Protection All Short Evil
category: entities
---

# Effect Protection All Short Evil

This entity defines a short-duration, all-element protection effect, often associated with "evil" or negative status effects in Noita. It grants temporary immunity to various damage types and status ailments.

## Key Components

### GameEffectComponent

This component defines the specific protective effects granted by the entity.

| Attribute | Description |
|---|---|
| `_tags` | Identifies the effect (e.g., `protection_all_short`, `effect_protection_all`). |
| `effect` | The type of protection granted. This entity applies: <br> - `PROTECTION_ALL`: General protection. <br> - `PROTECTION_FREEZE`: Immunity to freezing. <br> - `PROTECTION_FIRE`: Immunity to fire damage. |
| `frames` | The duration of each individual protection effect in game frames (120 frames ≈ 2 seconds). |

### LifetimeComponent

Determines how long the entity itself persists before despawning.

| Attribute | Description |
|---|---|
| `lifetime` | The total duration of the entity in game frames. |

### SpriteParticleEmitterComponent

Manages the visual particle effects associated with this entity.

| Attribute | Description |
|---|---|
| `sprite_file` | Path to the particle sprite definition (`data/particles/protection_all_evil.xml`). |
| `delay` | Initial delay before particle emission starts. |
| `lifetime` | Duration of each emitted particle. |
| `color.r`, `color.g`, `color.b`, `color.a` | Initial color of the particles. |
| `color_change.r`, `color_change.g`, `color_change.b`, `color_change.a` | How the color changes over the particle's lifetime. |
| `velocity.x`, `velocity.y` | Base velocity of emitted particles. |
| `gravity.x`, `gravity.y` | Gravity applied to particles. |
| `velocity_slowdown` | How quickly particles lose velocity. |
| `scale.x`, `scale.y` | Initial scale of particles. |
| `scale_velocity.x`, `scale_velocity.y` | How particle scale changes over time. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Range for the time between particle emissions. |
| `count_min`, `count_max` | Range for the number of particles emitted per burst. |
| `randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y` | Random offset for particle spawn position. |
| `randomize_velocity.min_y`, `randomize_velocity.max_y` | Random variation in particle vertical velocity. |