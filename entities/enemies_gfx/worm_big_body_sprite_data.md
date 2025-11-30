---
title: Worm Big Body Sprite Data
category: entities/enemies_gfx
---

# Worm Big Body Sprite Data

This document details the sprite data for the "worm_big_body" enemy in Noita, focusing on its visual representation and animations.

## Sprite Definition

The primary sprite for the worm's big body segment is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_big_body.png` - The image file containing the sprite frames.
*   **offset_x**: `14` - Horizontal offset for the sprite.
*   **offset_y**: `12` - Vertical offset for the sprite.
*   **default_animation**: `stand` - The animation that plays by default.

## Animations

The sprite supports multiple animations, defined by `<RectAnimation>` tags.

### `stand` Animation

This animation likely represents the worm's idle or standing pose.

#### Key Attributes:

*   **name**: `stand`
*   **frame_count**: `4` - Total number of frames in this animation.
*   **frame_width**: `29` - Width of each individual frame.
*   **frame_height**: `26` - Height of each individual frame.
*   **frames_per_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **frame_wait**: `0.082` - Delay between frames in seconds.
*   **pos_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos_y**: `1` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **shrink_by_one_pixel**: `1` - Indicates if frames should be shrunk by one pixel.

### `eat` Animation

This animation likely represents the worm's eating action.

#### Key Attributes:

*   **name**: `eat`
*   **frame_count**: `4` - Total number of frames in this animation.
*   **frame_width**: `29` - Width of each individual frame.
*   **frame_height**: `26` - Height of each individual frame.
*   **frames_per_row**: `4` - Number of frames arranged horizontally in the sprite sheet.
*   **frame_wait**: `0.082` - Delay between frames in seconds.
*   **pos_x**: `0` - X-coordinate of the animation's top-left corner within the sprite sheet.
*   **pos_y**: `1` - Y-coordinate of the animation's top-left corner within the sprite sheet.
*   **shrink_by_one_pixel**: `1` - Indicates if frames should be shrunk by one pixel.