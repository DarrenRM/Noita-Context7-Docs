---
title: Energy Shield Sector 016 Particle
category: particles
---

# Energy Shield Sector 016 Particle

This document describes the `energy_shield_sector_016.xml` particle definition, used for visual effects in Noita.

## Sprite Definition

The primary visual representation of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/energy_shield_sector_016.png` - Specifies the texture file used for the sprite.
*   **`offset_x`**: `16` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `16` - Vertical offset for the sprite's origin.

## Animations

This particle utilizes two distinct animations: `default` and `hit`.

### `default` Animation

This is the primary, looping animation for the energy shield.

#### Key Attributes:

*   **`name`**: `default`
*   **`frame_count`**: `6` - The total number of frames in this animation.
*   **`frame_width`**: `33` - The width of each frame in pixels.
*   **`frame_height`**: `33` - The height of each frame in pixels.
*   **`frames_per_row`**: `6` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.03` - The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: `0` - The starting X coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates that each frame should be shrunk by one pixel, likely for animation effects.

### `hit` Animation

This animation is triggered when the shield is hit and is designed to play only once.

#### Key Attributes:

*   **`name`**: `hit`
*   **`frame_count`**: `1` - This animation consists of a single frame.
*   **`frame_width`**: `32` - The width of the frame in pixels.
*   **`frame_height`**: `32` - The height of the frame in pixels.
*   **`frames_per_row`**: `6` - Although only one frame is used, this attribute is still defined.
*   **`frame_wait`**: `0.1` - The duration (in seconds) this single frame is displayed.
*   **`loop`**: `0` - Specifies that this animation does not loop.
*   **`pos_x`**: `0` - The starting X coordinate of the animation frame within the sprite sheet.
*   **`pos_y`**: `34` - The starting Y coordinate of the animation frame within the sprite sheet.