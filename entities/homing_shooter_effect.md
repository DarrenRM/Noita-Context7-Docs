---
title: Homing Shooter Effect
category: entities
---

# Homing Shooter Effect

This entity defines the visual and functional components for the "Homing Shooter" status effect in Noita. It's primarily used to apply a homing behavior to projectiles fired by the player.

## Key Components

### ShotEffectComponent

This component dictates the special effect applied to projectiles.

| Attribute          | Description                                                                 |
| :----------------- | :-------------------------------------------------------------------------- |
| `extra_modifier`   | Specifies the modifier to be applied, in this case, `projectile_homing_shooter_wizard`. This modifier likely grants the homing property. |

### LifetimeComponent

Determines how long the effect persists.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The duration of the effect in frames (1200 frames = 20 seconds). |

### UIIconComponent

Manages the display of the status effect in the game's user interface.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `name`                | The internal name for the status effect, linked to localization (`$status_homing_shooter`). |
| `description`         | The descriptive text for the status effect, linked to localization (`$statusdesc_homing_shooter`). |
| `icon_sprite_file`    | The path to the sprite used for the status icon in the UI.                  |
| `is_perk`             | Indicates if this is a perk (0 means it's not a perk).                      |
| `display_above_head`  | Whether the icon is displayed above the player's head (0 means no).         |
| `display_in_hud`      | Whether the icon is displayed in the Heads-Up Display (1 means yes).        |