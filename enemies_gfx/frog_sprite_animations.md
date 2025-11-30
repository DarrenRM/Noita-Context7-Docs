---
title: Frog Sprite Animations
category: entities_gfx
---

# Frog Sprite Animations

This document details the sprite animations for the Frog enemy in Noita, as defined in `frog.xml`. It focuses on the key attributes that control its visual appearance and behavior during animations.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and global offsets for all animations.

### Key Attributes:

*   **filename**: The path to the sprite sheet image.
    *   `data/enemies_gfx/frog.png`
*   **offset\_x**: Horizontal offset of the sprite from its origin.
    *   `10`
*   **offset\_y**: Vertical offset of the sprite from its origin.
    *   `16`
*   **default\_animation**: The animation to play by default.
    *   `stand`

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Stand Animation

The default animation for the frog.

*   **name**: `stand`
*   **pos\_x**: Starting X coordinate on the sprite sheet.
    *   `0`
*   **pos\_y**: Starting Y coordinate on the sprite sheet.
    *   `20`
*   **frame\_count**: Total number of frames in the animation.
    *   `8`
*   **frame\_width**: Width of each individual frame.
    *   `20`
*   **frame\_height**: Height of each individual frame.
    *   `20`
*   **frame\_wait**: Duration each frame is displayed.
    *   `0.16`
*   **frames\_per\_row**: Number of frames in a single row of the sprite sheet.
    *   `8`
*   **loop**: Whether the animation should loop.
    *   `1` (true)

### Jump Up Animation

The animation played when the frog initiates a jump.

*   **name**: `jump_up`
*   **pos\_x**: `0`
*   **pos\_y**: `20`
*   **frame\_count**: `1`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `8`
*   **loop**: `0` (false)
*   **Events**:
    *   **frame**: `0`
    *   **name**: `jump`
    *   **probability**: `1`
    *   **check\_physics\_material**: `1` (true)

### Jump Falling Animation

The animation played while the frog is falling after a jump.

*   **name**: `jump_fall`
*   **pos\_x**: `0`
*   **pos\_y**: `40`
*   **frame\_count**: `1`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `8`
*   **loop**: `0` (false)

### Land Animation

The animation played when the frog lands after a jump.

*   **name**: `land`
*   **pos\_x**: `0`
*   **pos\_y**: `60`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `20`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `8`
*   **loop**: `0` (false)
*   **Events**:
    *   **frame**: `0`
    *   **name**: `land`
    *   **probability**: `1`
    *   **check\_physics\_material**: `1` (true)