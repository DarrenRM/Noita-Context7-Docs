---
title: Berserk Spirit Effect
category: entities
---

# Berserk Spirit Effect

This entity defines the visual and functional aspects of the "Berserk" status effect in Noita, often applied by spirits.

## Core Components

### GameEffectComponent
This component dictates the primary effect applied to the entity.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `BERSERK` | Specifies the type of game effect. |
| `frames` | `120` | Duration of the effect in frames (2 seconds at 60 FPS). |

### LifetimeComponent
Controls how long the entity itself persists.

| Attribute | Value | Description |
|---|---|---|
| `lifetime` | `100` | Duration of the entity's existence in frames. |

### UIIconComponent
Manages the display of the status effect in the game's UI.

| Attribute | Value | Description |
|---|---|---|
| `name` | `$status_berserk` | Localized name of the status effect. |
| `description` | `$statusdesc_berserk` | Localized description of the status effect. |
| `icon_sprite_file` | `data/ui_gfx/status_indicators/berserk.png` | Path to the icon displayed in the HUD. |
| `display_in_hud` | `1` | Ensures the icon is shown in the Heads-Up Display. |

## Visual Effects (SpriteParticleEmitterComponent)

This component generates particles to visually represent the Berserk effect.

| Attribute | Value | Description |
|---|---|---|
| `sprite_file` | `data/particles/berserk_0$[1-4].xml` | Specifies the particle sprite files to use, with randomization. |
| `lifetime` | `1.5` | Duration of each individual particle in seconds. |
| `color.r`, `color.g`, `color.b`, `color.a` | `1` | Initial color of the particles (white). |
| `color_change.a` | `-0.5` | Alpha (transparency) change per second, causing particles to fade out. |
| `gravity.y` | `10` | Downward gravity applied to particles. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `10`, `20` | Controls the timing between particle emissions. |
| `count_min`, `count_max` | `1`, `1` | Number of particles emitted per interval. |
| `randomize_rotation.min`, `randomize_rotation.max` | `-0.3415`, `0.3415` | Randomizes the initial rotation of particles. |
| `randomize_position.min_x`, `randomize_position.max_x` | `-5`, `5` | Randomizes the horizontal spawn position of particles. |
| `randomize_position.min_y`, `randomize_position.max_y` | `-10`, `0` | Randomizes the vertical spawn position of particles. |
| `randomize_velocity.min_x`, `randomize_velocity.max_x` | `-10`, `10` | Randomizes the horizontal initial velocity of particles. |
| `randomize_velocity.min_y`, `randomize_velocity.max_y` | `-20`, `5` | Randomizes the vertical initial velocity of particles. |