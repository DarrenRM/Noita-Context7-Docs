---
title: Effect Spirit Weakness
category: entities
---

# Effect Spirit Weakness

This entity defines the "Weakness" status effect in Noita, often applied by spirits. It visually represents the effect with particles and provides UI feedback.

## Key Components

### `GameEffectComponent`

This component defines the core game effect.

| Attribute | Value | Description |
|---|---|---|
| `_tags` | `spirit_weakness` | Internal tag for this specific effect. |
| `effect` | `WEAKNESS` | The type of game effect applied. |
| `frames` | `120` | Duration of the effect in frames (2 seconds at 60 FPS). |

### `LifetimeComponent`

Determines how long the entity itself persists.

| Attribute | Value | Description |
|---|---|---|
| `lifetime` | `100` | Duration of the entity's existence in frames. |

### `SpriteParticleEmitterComponent`

Responsible for the visual particle effects associated with the weakness.

| Attribute | Value | Description |
|---|---|---|
| `sprite_file` | `data/particles/creepy.xml` | The particle sprite definition to use. |
| `color.a` | `0.4` | Initial transparency of the particles. |
| `color_change.a` | `-1` | The rate at which particles fade out. |
| `emission_interval_min_frames` | `20` | Minimum frames between particle emissions. |
| `emission_interval_max_frames` | `30` | Maximum frames between particle emissions. |
| `count_min` | `1` | Minimum particles emitted per interval. |
| `count_max` | `1` | Maximum particles emitted per interval. |
| `randomize_position` | `-2` to `2` (x/y) | Random offset for particle emission position. |
| `randomize_velocity` | `-8` to `8` (x/y) | Random initial velocity for particles. |

### `UIIconComponent`

Manages the UI representation of the status effect.

| Attribute | Value | Description |
|---|---|---|
| `name` | `$status_weakness` | Localized name of the status effect. |
| `description` | `$statusdesc_weakness` | Localized description of the status effect. |
| `icon_sprite_file` | `data/ui_gfx/status_indicators/weakness.png` | The icon displayed in the UI. |
| `display_in_hud` | `1` | Indicates the icon should be shown in the HUD. |

## Other Components

*   **`InheritTransformComponent`**: This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting transformations.