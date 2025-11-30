---
title: Leukaluu Wand Configuration
category: scripts/gun/procedural
---

---

# Leukaluu Wand Configuration

This document details the configuration for the "Leukaluu" wand, focusing on its visual and UI elements.

## Visuals

### Sprite Configuration

*   **`sprite_path`**: `data/items_gfx/wands/custom/leukaluu.png`
    *   Specifies the image file used for the wand's sprite.
*   **`sprite_offset_x`**: `3`
    *   Horizontal offset for the sprite.
*   **`sprite_offset_y`**: `5`
    *   Vertical offset for the sprite.

## UI Elements

### Item Component Configuration

*   **`item_name`**: `"$item_leukaluu"`
    *   The internal name for the wand, used for referencing.
*   **`ui_sprite`**: `data/items_gfx/wands/custom/leukaluu.png`
    *   The sprite used in the UI (inventory, hotbar).
*   **`always_use_item_name_in_ui`**: `true`
    *   Ensures the custom `item_name` is always displayed in the UI, overriding default naming conventions.