---
title: Walleye Sprite Animation
category: data/buildings_gfx
---

# Walleye Sprite Animation

This document describes the sprite animations for the "Walleye" entity in Noita.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and default animation.

### Key Attributes:

*   **filename**: `data/buildings_gfx/walleye.png` - The path to the sprite sheet.
*   **offset_x**: `12` - Horizontal offset for the sprite.
*   **offset_y**: `8` - Vertical offset for the sprite.
*   **default_animation**: `stand` - The animation to play by default.

## Animations

The Walleye entity has two defined animations: `stand` and `blink`.

### `stand` Animation

This is the default idle animation.

#### Key Attributes:

*   **name**: `stand`
*   **frame_count**: `1` - Number of frames in this animation.
*   **frame_width**: `24` - Width of each frame.
*   **frame_height**: `16` - Height of each frame.
*   **frames_per_row**: `7` - How many frames are in a single row of the sprite sheet.
*   **frame_wait**: `0.1` - Time in seconds to wait between frames.
*   **pos_x**: `0` - X-coordinate of the animation's starting position on the sprite sheet.
*   **pos_y**: `0` - Y-coordinate of the animation's starting position on the sprite sheet.

### `blink` Animation

This animation simulates the Walleye blinking.

#### Key Attributes:

*   **name**: `blink`
*   **frame_count**: `9` - Number of frames in this animation.
*   **frame_width**: `24` - Width of each frame.
*   **frame_height**: `16` - Height of each frame.
*   **frames_per_row**: `9` - How many frames are in a single row of the sprite sheet.
*   **frame_wait**: `0.05` - Time in seconds to wait between frames.
*   **pos_x**: `0` - X-coordinate of the animation's starting position on the sprite sheet.
*   **pos_y**: `16` - Y-coordinate of the animation's starting position on the sprite sheet.
*   **next_animation**: `stand` - The animation to transition to after `blink` finishes.
*   **loop**: `0` - This animation does not loop.