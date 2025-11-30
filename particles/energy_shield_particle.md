---
title: Energy Shield Particle
category: particles
---

# Energy Shield Particle

This document describes the `energy_shield_016.xml` particle, which is used to represent an energy shield effect in Noita.

## Sprite Definition

The primary sprite definition for this particle is handled by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. Here, it's set to "default".
*   **`filename`**: The path to the sprite sheet image file.
*   **`offset_x`**, **`offset_y`**: These attributes define the center point of the sprite relative to its origin.

## Animations

This particle utilizes two distinct animations defined by `<RectAnimation>` tags.

### `default` Animation

This animation likely represents the idle or active state of the energy shield.

#### Key Attributes:

*   **`name`**: "default" - Identifies this animation.
*   **`frame_count`**: 6 - The total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: 33 - The dimensions of each individual frame.
*   **`frames_per_row`**: 6 - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: 0.03 - The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**, **`pos_y`**: 0, 1 - The starting position (top-left corner) of this animation's frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: 1 - Indicates that each frame should be shrunk by one pixel, likely for visual effect or to avoid sprite bleeding.

### `hit` Animation

This animation is likely triggered when the energy shield is struck or damaged.

#### Key Attributes:

*   **`name`**: "hit" - Identifies this animation.
*   **`frame_count`**: 1 - This animation consists of a single frame.
*   **`frame_width`**, **`frame_height`**: 33 - The dimensions of the frame.
*   **`frames_per_row`**: 6 - The number of frames per row in the sprite sheet.
*   **`frame_wait`**: 0.1 - The duration each frame is displayed.
*   **`loop`**: 0 - This animation does not loop, meaning it plays only once.
*   **`pos_x`**, **`pos_y`**: 0, 34 - The starting position of this animation's frames within the sprite sheet. Note that `pos_y` is 34, indicating it's on a different row than the "default" animation.
*   **`shrink_by_one_pixel`**: 1 - Similar to the default animation, this frame is also shrunk.