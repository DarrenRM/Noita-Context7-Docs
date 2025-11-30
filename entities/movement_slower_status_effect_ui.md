---
title: Movement Slower Status Effect UI
category: entities
---

# Movement Slower Status Effect UI

This entity defines the user interface elements for the "Movement Slower" status effect in Noita. It dictates how the effect is displayed to the player, including its icon and descriptive text.

## Key Components

### GameEffectComponent

This component specifies the actual game effect associated with this UI element.

| Attribute | Value        | Description                                   |
| :-------- | :----------- | :-------------------------------------------- |
| `effect`  | `MOVEMENT_SLOWER` | The internal identifier for the movement slowing effect. |
| `frames`  | `600`        | The duration of the effect in frames (approximately 10 seconds). |

### UIIconComponent

This component handles the visual representation of the status effect in the game's user interface.

| Attribute           | Value                                       | Description                                                                 |
| :------------------ | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `name`              | `$status_movement_slower_ui`                | The localization key for the status effect's name displayed in the UI.      |
| `description`       | `$statusdesc_movement_slower_ui`            | The localization key for the status effect's description displayed in the UI. |
| `icon_sprite_file`  | `data/ui_gfx/status_indicators/movement_slower.png` | The file path to the sprite used for the status effect's icon.              |
| `is_perk`           | `0`                                         | Indicates that this is not a perk, but a status effect.                     |
| `display_above_head`| `0`                                         | The icon will not be displayed directly above the player's head.            |
| `display_in_hud`    | `1`                                         | The icon will be displayed in the Heads-Up Display (HUD).                   |

## Inheritance

### InheritTransformComponent

This component is present but empty, indicating that the entity inherits standard transform properties without any specific modifications.