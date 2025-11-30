---
title: Wand Vasta Configuration
category: scripts
---

---

# Wand Vasta Configuration

This document details the configuration for the "Vasta" wand, focusing on its visual and UI elements.

## Visual and UI Configuration

This section describes how the wand's appearance and in-game name are set.

### Sprite and Item Components

The following components are modified to define the wand's visual representation and its display name in the game's user interface.

| Component Type   | Attribute      | Value                                     | Description                                                              |
| :--------------- | :------------- | :---------------------------------------- | :----------------------------------------------------------------------- |
| `SpriteComponent`| `image_file`   | `data/items_gfx/wands/custom/vasta.png`   | Specifies the image file used for the wand's sprite.                     |
| `SpriteComponent`| `offset_x`     | `3`                                       | Horizontal offset for the sprite.                                        |
| `SpriteComponent`| `offset_y`     | `6.5`                                     | Vertical offset for the sprite.                                          |
| `ItemComponent`  | `ui_sprite`    | `data/items_gfx/wands/custom/vasta.png`   | The sprite used for the item in the UI.                                  |
| `ItemComponent`  | `item_name`    | `$item_vasta`                             | The internal identifier for the wand's name, likely localized.           |
| `ItemComponent`  | `always_use_item_name_in_ui` | `true`                                    | Ensures the custom item name is always displayed in the UI.              |