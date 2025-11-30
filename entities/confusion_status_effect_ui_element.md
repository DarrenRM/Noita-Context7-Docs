---
title: Confusion Status Effect UI Element
category: entities
---

# Confusion Status Effect UI Element

This entity defines the visual representation and behavior of the "Confusion" status effect when displayed in the game's UI.

## Key Components

### `GameEffectComponent`

This component links the entity to the game's effect system.

| Attribute | Value   | Description                                  |
| :-------- | :------ | :------------------------------------------- |
| `effect`  | `CONFUSION` | Specifies the type of game effect.           |
| `frames`  | `1000`  | Duration of the effect in frames (approx. 16.6 seconds). |

### `SpriteParticleEmitterComponent`

This component generates visual particles to accompany the status effect.

| Attribute                 | Value                               | Description                                                              |
| :------------------------ | :---------------------------------- | :----------------------------------------------------------------------- |
| `sprite_file`             | `data/particles/shine_confusion.xml` | Path to the particle sprite definition.                                  |
| `delay`                   | `0`                                 | Delay before particle emission starts.                                   |
| `lifetime`                | `0`                                 | Lifetime of individual particles (0 means it uses the sprite's lifetime). |
| `color.r`, `color.g`, `color.b`, `color.a` | `1`                                 | Initial color of the particles (white).                                  |
| `gravity.y`               | `10`                                | Downward gravitational pull on particles.                                |
| `emission_interval_min_frames` | `1`                                 | Minimum frames between particle emissions.                               |
| `emission_interval_max_frames` | `2`                                 | Maximum frames between particle emissions.                               |
| `count_min`               | `1`                                 | Minimum number of particles emitted per burst.                           |
| `count_max`               | `4`                                 | Maximum number of particles emitted per burst.                           |
| `randomize_rotation.min`  | `-3.1415`                           | Minimum random rotation for particles.                                   |
| `randomize_rotation.max`  | `3.1415`                            | Maximum random rotation for particles.                                   |
| `randomize_position.min_x` | `-4`                                | Minimum random X offset for particle spawn position.                     |
| `randomize_position.max_x` | `4`                                 | Maximum random X offset for particle spawn position.                     |
| `randomize_position.min_y` | `-4`                                | Minimum random Y offset for particle spawn position.                     |
| `randomize_position.max_y` | `4`                                 | Maximum random Y offset for particle spawn position.                     |

### `UIIconComponent`

This component defines how the status effect is displayed in the user interface.

| Attribute             | Value                               | Description                                                              |
| :-------------------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `name`                | `$status_confusion_ui`              | Internal name for the UI element (likely linked to localization).        |
| `description`         | `$statusdesc_confusion_ui`          | Internal name for the UI element's description (likely linked to localization). |
| `icon_sprite_file`    | `data/ui_gfx/status_indicators/confusion.png` | Path to the icon image used in the UI.                                   |
| `display_in_hud`      | `1`                                 | Indicates that this status effect should be displayed in the HUD.        |
| `display_above_head`  | `0`                                 | Indicates that this status effect should NOT be displayed above the character's head. |