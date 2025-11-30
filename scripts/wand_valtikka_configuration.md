---
title: Wand Valtikka Configuration
category: scripts
---

---

# Wand Valtikka Configuration

This document details the configuration for the "Wand Valtikka" item in Noita, focusing on its visual and UI representation.

## Visuals

### Sprite Configuration

This section defines the visual appearance of the Wand Valtikka in the game.

| Attribute      | Value                                  | Description                                     |
| -------------- | -------------------------------------- | ----------------------------------------------- |
| `image_file`   | `"data/items_gfx/wands/custom/scepter_01.png"` | Path to the sprite image used for the wand.     |
| `offset_x`     | `3`                                    | Horizontal offset for the sprite.               |
| `offset_y`     | `5`                                    | Vertical offset for the sprite.                 |

## User Interface (UI)

### Item Component Configuration

This section configures how the Wand Valtikka is displayed and identified within the game's UI.

| Attribute                 | Value                                  | Description                                                              |
| ------------------------- | -------------------------------------- | ------------------------------------------------------------------------ |
| `ui_sprite`               | `"data/items_gfx/wands/custom/scepter_01.png"` | Sprite used in UI elements (e.g., inventory, hotbar).                    |
| `item_name`               | `"$item_wand_valtikka"`                | The internal name identifier for the item, used for localization.        |
| `always_use_item_name_in_ui` | `true`                                 | Ensures the `item_name` is always displayed in the UI, overriding defaults. |