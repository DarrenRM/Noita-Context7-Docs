---
title: Spore Pod Projectile Graphics
category: projectiles_gfx
---

# Spore Pod Projectile Graphics

This document details the graphical assets for the "spore_pod" projectile in Noita, focusing on its sprite and animations.

## Sprite Definition

The main sprite for the spore pod is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/spore_pod.png` - The path to the sprite sheet.
*   **offset_x**: `7` - Horizontal offset for the sprite's origin.
*   **offset_y**: `10` - Vertical offset for the sprite's origin.
*   **default_animation**: `grow` - The animation to play by default.

## Animations

The spore pod projectile utilizes two distinct animations: `grow` and `pod`.

### `grow` Animation

This animation likely represents the initial growth or spawning phase of the spore pod.

#### Key Attributes:

*   **name**: `grow`
*   **pos_x**: `0` - Starting X position within the sprite sheet.
*   **pos_y**: `0` - Starting Y position within the sprite sheet.
*   **frame_count**: `7` - The total number of frames in this animation.
*   **frame_width**: `16` - The width of each individual frame.
*   **frame_height**: `16` - The height of each individual frame.
*   **frame_wait**: `0.09` - The duration (in seconds) each frame is displayed.
*   **frames_per_row**: `7` - How many frames are arranged horizontally on the sprite sheet.
*   **loop**: `0` - Indicates that this animation does not loop (plays once).

### `pod` Animation

This animation is likely a static or very short animation representing the mature spore pod.

#### Key Attributes:

*   **name**: `pod`
*   **pos_x**: `0`
*   **pos_y**: `0`
*   **frame_count**: `1` - This animation consists of a single frame.
*   **frame_width**: `16`
*   **frame_height**: `16`
*   **frame_wait**: `0.09`
*   **frames_per_row**: `1`
*   **loop**: `0` - This animation also does not loop.