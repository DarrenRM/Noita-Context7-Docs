---
title: Twitchy Status Effect Entity
category: entities
---

# Twitchy Status Effect Entity

This entity defines the "Twitchy" status effect in Noita, primarily managed by Lua scripts. It dictates how the effect behaves, its duration, and how it's represented in the game's UI.

## Key Components

### LuaComponent (Primary Logic)

This component is responsible for executing the core logic of the Twitchy status effect.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `script_source_file` | Path to the Lua script that handles the general behavior of the status effect. |
| `execute_every_n_frame` | The frequency (in frames) at which the `script_source_file` is executed. A value of `60` means it runs every 60 frames. |

### LuaComponent (Shot Logic)

This component handles any specific logic related to projectiles or attacks when the Twitchy status effect is active.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `script_shot`       | Path to the Lua script that manages shot-related behavior for the status effect. |
| `execute_every_n_frame` | Set to `-1`, indicating this script is likely called on demand or by other game events rather than a fixed frame interval. |

### LifetimeComponent

Determines how long the Twitchy status effect persists on an entity.

| Attribute | Description                                                                 |
| :-------- | :-------------------------------------------------------------------------- |
| `lifetime` | The duration of the status effect in seconds (1200 seconds = 20 minutes). |

### UIIconComponent

Defines how the Twitchy status effect is displayed to the player in the game's user interface.

| Attribute          | Description                                                                 |
| :----------------- | :-------------------------------------------------------------------------- |
| `name`             | The internal name or localization key for the status effect's display name. |
| `description`      | The localization key for the status effect's description text.              |
| `icon_sprite_file` | The path to the image file used for the status effect's icon.               |
| `is_perk`          | Indicates if this is a perk (`0` means it's a status effect, not a perk).   |
| `display_above_head` | Whether the icon should be displayed above the character's head (`0` means no). |
| `display_in_hud`   | Whether the icon should be displayed in the Heads-Up Display (`1` means yes). |