---
title: Wand Arpaluu Configuration
category: scripts
---

# Wand Arpaluu Configuration

This document details the configuration for the "Arpaluu" wand in Noita, focusing on its visual and UI elements.

## Core Configuration

This wand is primarily defined by its visual appearance and how it's presented in the game's UI.

### Visuals

*   **`name`**: `$item_wand_arpaluu` - The internal and UI name for the wand.
*   **`sprite_path`**: `"data/items_gfx/wands/custom/skull_01.png"` - Specifies the image file used for the wand's sprite.
*   **`sprite_offset_x`**: `3` - Horizontal offset for the sprite.
*   **`sprite_offset_y`**: `5` - Vertical offset for the sprite.

### UI Presentation

*   **`ui_sprite`**: Inherits from `sprite_path`. This is the sprite displayed in the UI.
*   **`item_name`**: Inherits from `name`. The name displayed in the UI.
*   **`always_use_item_name_in_ui`**: `true` - Ensures the custom `item_name` is always used in the UI, overriding default naming conventions.

## Script Dependencies

This configuration relies on external utility scripts:

*   `dofile("data/scripts/lib/utilities.lua")`
*   `dofile("data/scripts/gun/procedural/gun_action_utils.lua")`