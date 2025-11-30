---
title: Dark Ghost Sprite Definitions
category: entities/enemies_gfx
---

# Dark Ghost Sprite Definitions

This document details the sprite definitions for the Dark Ghost enemy in Noita, as found in `darkghost.xml`. It outlines the visual assets and animations used to render this enemy.

## Sprite Attributes

The primary `Sprite` tag defines the base image and its positioning.

*   **filename**: `data/enemies_gfx/darkghost.png` - The path to the sprite sheet containing all frames for the Dark Ghost.
*   **offset\_x**: `24` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `24` - Vertical offset for the sprite's origin.
*   **default\_animation**: `stand` - The animation that plays by default when the enemy is idle.

## Animations

The `Sprite` tag contains multiple `RectAnimation` tags, each defining a specific animation sequence.

### `stand` Animation

This animation represents the Dark Ghost in its idle state.

*   **name**: `stand`
*   **pos\_x**: `0` - Starting X coordinate on the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y coordinate on the sprite sheet for this animation.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `48` - The width of each individual frame.
*   **frame\_height**: `48` - The height of each individual frame.
*   **frame\_wait**: `0.08` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally on the sprite sheet for this animation.
*   **loop**: `1` - Indicates that this animation should loop continuously.

### `blink` Animation

This animation defines the Dark Ghost's blinking action.

*   **name**: `blink`
*   **pos\_x**: `0` - Starting X coordinate on the sprite sheet for this animation.
*   **pos\_y**: `0` - Starting Y coordinate on the sprite sheet for this animation.
*   **frame\_count**: `11` - The total number of frames in this animation.
*   **frame\_width**: `48` - The width of each individual frame.
*   **frame\_height**: `48` - The height of each individual frame.
*   **frame\_wait**: `0.08` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `11` - The number of frames arranged horizontally on the sprite sheet for this animation.
*   **loop**: `0` - Indicates that this animation should play only once and not loop.