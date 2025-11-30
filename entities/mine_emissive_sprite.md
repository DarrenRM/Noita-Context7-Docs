---
title: Mine Emissive Sprite
category: entities
---

# Mine Emissive Sprite

This document describes the sprite data for the "Mine" enemy, specifically its emissive graphical components.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/mine_emissive.png` - The path to the sprite sheet.
*   **offset\_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `6` - Vertical offset for the sprite's origin.
*   **default\_animation**: `stand` - The animation to play by default.

## Animations

The sprite sheet contains multiple animations defined by `<RectAnimation>` tags.

### `stand` Animation

This animation represents the mine's idle or standing state.

*   **name**: `stand`
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `0` - Starting Y position on the sprite sheet.
*   **frame\_count**: `1` - Number of frames in this animation.
*   **frame\_width**: `12` - Width of each individual frame.
*   **frame\_height**: `12` - Height of each individual frame.
*   **frame\_wait**: `0.16` - Time in seconds each frame is displayed.
*   **frames\_per\_row**: `8` - Number of frames horizontally on the sprite sheet.
*   **loop**: `1` - Whether the animation should loop (1 for true, 0 for false).

### `detonate` Animation

This animation likely represents the mine's detonation sequence.

*   **name**: `detonate`
*   **pos\_x**: `0` - Starting X position on the sprite sheet.
*   **pos\_y**: `0` - Starting Y position on the sprite sheet.
*   **frame\_count**: `8` - Number of frames in this animation.
*   **frame\_width**: `12` - Width of each individual frame.
*   **frame\_height**: `12` - Height of each individual frame.
*   **frame\_wait**: `0.09` - Time in seconds each frame is displayed.
*   **frames\_per\_row**: `8` - Number of frames horizontally on the sprite sheet.
*   **loop**: `1` - Whether the animation should loop.