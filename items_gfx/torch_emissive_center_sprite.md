---
title: Torch Emissive Center Sprite
category: items_gfx
---

# Torch Emissive Center Sprite

This document details the sprite definition for the `torch_emissive_center` item in Noita, focusing on its visual representation and animations.

## Sprite Definition

The core sprite is defined by the `<Sprite>` tag, which specifies the base image file and its positioning.

### Key Attributes:

*   **`filename`**: `data/items_gfx/torch_emissive_center.png`
    *   The path to the image file containing the sprite frames.
*   **`offset_x`**: `16.5`
    *   Horizontal offset of the sprite's origin.
*   **`offset_y`**: `20.0`
    *   Vertical offset of the sprite's origin.
*   **`default_animation`**: `default`
    *   The name of the animation that plays by default.

## Animations

The sprite supports multiple animations, each defined by a `<RectAnimation>` tag. These animations control how the sprite changes over time, creating visual effects.

### Animation Details:

#### `default` Animation

This is the primary animation for the torch's emissive center.

*   **`name`**: `default`
*   **`pos_x`**: `0`
*   **`pos_y`**: `0`
*   **`frame_count`**: `4`
    *   Number of frames in this animation.
*   **`frame_width`**: `32`
    *   Width of each individual frame.
*   **`frame_height`**: `32`
    *   Height of each individual frame.
*   **`frame_wait`**: `0.09`
    *   Time in seconds to wait between frames.
*   **`frames_per_row`**: `4`
    *   Number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `1`
    *   Indicates that the animation should loop (1 for true, 0 for false).

#### `appear` Animation

This animation likely plays when the torch's emissive center becomes visible.

*   **`name`**: `appear`
*   **`pos_x`**: `0`
*   **`pos_y`**: `32`
    *   This offset indicates the starting row for this animation's frames within the sprite sheet.
*   **`frame_count`**: `5`
*   **`frame_width`**: `32`
*   **`frame_height`**: `32`
*   **`frame_wait`**: `0.05`
*   **`frames_per_row`**: `5`
*   **`loop`**: `0`
    *   This animation does not loop.

#### `out` Animation

This animation might be used for a fading out effect, though `frame_count` is 0.

*   **`name`**: `out`
*   **`pos_x`**: `0`
*   **`pos_y`**: `96`
*   **`frame_count`**: `0`
    *   A `frame_count` of 0 suggests this animation might be a placeholder or have no visual frames defined here.
*   **`frame_width`**: `32`
*   **`frame_height`**: `32`
*   **`frame_wait`**: `0.09`
*   **`frames_per_row`**: `4`
*   **`loop`**: `1`

#### `disappear` Animation

This animation likely plays when the torch's emissive center fades away.

*   **`name`**: `disappear`
*   **`pos_x`**: `0`
*   **`pos_y`**: `64`
    *   This offset indicates the starting row for this animation's frames.
*   **`frame_count`**: `3`
*   **`frame_width`**: `32`
*   **`frame_height`**: `32`
*   **`frame_wait`**: `0.05`
*   **`frames_per_row`**: `4`
*   **`loop`**: `0`
    *   This animation does not loop.