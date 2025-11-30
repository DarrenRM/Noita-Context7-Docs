---
title: Potion Mimic Indicator
category: biome
---

# Potion Mimic Indicator

This entity defines the visual indicator for potion mimics in Noita. It's a simple entity that displays a small icon above a mimic to alert the player.

## LuaComponent

This component handles the logic for the indicator.

### Key Attributes:

*   **`script_source_file`**: Specifies the Lua script responsible for the indicator's behavior.
    *   `data/biome_impl/static_tile/potion_mimics_indicator.lua`
*   **`execute_every_n_frame`**: Determines how often the script's logic is executed.
    *   `2`: The script runs every 2 frames.

## SpriteComponent

This component defines the visual appearance of the indicator.

### Key Attributes:

*   **`offset_x`**: Horizontal offset of the sprite.
    *   `4`
*   **`offset_y`**: Vertical offset of the sprite.
    *   `4`
*   **`image_file`**: The image file used for the indicator sprite.
    *   `data/biome_impl/static_tile/temples-assets/potion_mimic_icon.png`