---
title: Small Damage Plus Effect
category: entities
---

# Small Damage Plus Effect

This entity defines a status effect that slightly increases projectile damage.

## Key Components

### ShotEffectComponent

This component applies a modifier to projectiles.

| Attribute       | Value             | Description                                     |
| :-------------- | :---------------- | :---------------------------------------------- |
| `extra_modifier` | `damage_plus_small` | The specific damage modifier to apply.          |

### LifetimeComponent

Determines how long the effect lasts.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime` | `300` | Duration of the effect in game frames (300 frames = 5 seconds). |

### UIIconComponent

Defines how the status effect is displayed in the game's UI.

| Attribute           | Value                                         | Description                                                              |
| :------------------ | :-------------------------------------------- | :----------------------------------------------------------------------- |
| `name`              | `$status_damage_plus_small`                   | The internal name for the status effect (used for localization).         |
| `description`       | `$statusdesc_damage_plus_small`               | The description text for the status effect (used for localization).      |
| `icon_sprite_file`  | `data/ui_gfx/status_indicators/damage_plus_small.png` | Path to the sprite used for the status icon.                             |
| `is_perk`           | `0`                                           | Indicates this is not a perk, but a temporary status effect.             |
| `display_above_head`| `0`                                           | Whether the icon should appear above the player's head.                  |
| `display_in_hud`    | `1`                                           | Whether the icon should be displayed in the Heads-Up Display (HUD).      |