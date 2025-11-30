---
title: Confusion Spirit Entity
category: entities
---

# Confusion Spirit Entity

This entity defines the behavior and visual representation of the "Confusion" spirit effect in Noita. It applies a status effect that disorients the player or enemies.

## Key Components

### GameEffectComponent
This component is responsible for applying the actual game effect.

| Attribute | Description |
|---|---|
| `effect` | Specifies the type of effect to apply. In this case, it's `CONFUSION`. |
| `frames` | The duration of the effect in game frames (120 frames = 2 seconds). |

### LifetimeComponent
Determines how long the spirit entity itself exists.

| Attribute | Description |
|---|---|
| `lifetime` | The duration of the entity in game frames (100 frames = ~1.67 seconds). |

### SpriteParticleEmitterComponent
Manages the visual particles associated with the confusion effect.

| Attribute | Description |
|---|---|
| `sprite_file` | Path to the particle sprite definition (`data/particles/shine_confusion.xml`). |
| `emission_interval_min_frames` | Minimum frames between particle emissions. |
| `emission_interval_max_frames` | Maximum frames between particle emissions. |
| `count_min` | Minimum number of particles emitted per interval. |
| `count_max` | Maximum number of particles emitted per interval. |
| `randomize_rotation.min` | Minimum random rotation for emitted particles. |
| `randomize_rotation.max` | Maximum random rotation for emitted particles. |
| `randomize_position.min_x` | Minimum X-offset for particle emission position. |
| `randomize_position.max_x` | Maximum X-offset for particle emission position. |
| `randomize_position.min_y` | Minimum Y-offset for particle emission position. |
| `randomize_position.max_y` | Maximum Y-offset for particle emission position. |
| `gravity.y` | Vertical gravity applied to particles. |

### UIIconComponent
Defines how the confusion status is displayed in the user interface.

| Attribute | Description |
|---|---|
| `name` | The localized string key for the status name (`$status_confusion`). |
| `description` | The localized string key for the status description (`$statusdesc_confusion`). |
| `icon_sprite_file` | Path to the icon sprite for the status indicator (`data/ui_gfx/status_indicators/confusion.png`). |
| `display_in_hud` | Whether the icon should be displayed in the HUD. |