---
title: Magic Numbers - Debugging and Gameplay Tweaks
category: data
---

---

# Magic Numbers - Debugging and Gameplay Tweaks

This document outlines key "magic numbers" found in Noita's configuration, primarily focusing on disabling debug features and minor gameplay adjustments. These values are often used to control the visibility or behavior of certain game systems.

## Core Debugging Flags

These flags control the activation of various debugging tools and logging mechanisms. Setting them to `0` typically disables the feature.

| Attribute Name                      | Description                                                              | Default Value |
| :---------------------------------- | :----------------------------------------------------------------------- | :------------ |
| `DEBUG_KEYS_ENABLED`                | Enables or disables the use of debug keybinds within the game.           | `0`           |
| `DEBUG_EXTRA_SCREENSHOT_KEYS_ENABLED` | Enables or disables additional screenshot-related debug keybinds.        | `0`           |
| `DEBUG_SCREENSHOTTER_ENABLED`       | Enables or disables an automated screenshotting utility.                 | `0`           |
| `DEBUG_LOG_STD_COUT`                | Controls whether debug messages are logged to standard output.           | `0`           |
| `DEBUG_LOG_TODO_ERRORS`             | Controls logging of "TODO" related errors.                               | `0`           |
| `DEBUG_ENABLE_AUTOSAVE`             | Enables or disables an automatic save feature, often for debugging.      | `1`           |
| `DEBUG_LUA_REPORT_BIOME_SPAWN_ERRORS` | Controls reporting of errors related to biome entity spawning in Lua.    | `0`           |

## Gameplay and UI Tweaks

These numbers influence specific gameplay mechanics or UI elements.

| Attribute Name              | Description                                                              | Default Value |
| :-------------------------- | :----------------------------------------------------------------------- | :------------ |
| `ESC_QUITS_GAME`            | Determines if the Escape key immediately quits the game.                 | `0`           |
| `UI_PIXEL_FONT_GAME_LOG`    | Controls the use of a pixel font for the in-game log.                    | `1`           |
| `DESIGN_PLAYER_PICKUP_ENABLED` | Enables or disables the player's ability to pick up items.              | `0`           |
| `DESIGN_WAND_SLOTS_ARE_CONSUMED` | Affects whether wand slots are consumed when spells are added.           | `0`           |
| `DESIGN_ITEMCHEST_DROPS_ACTIONS` | Controls actions related to item chest drops.                            | `0`           |
| `STEAM_CLOUD_SIZE_WARNING`  | Controls warnings related to Steam Cloud save file size.                 | `1`           |

---