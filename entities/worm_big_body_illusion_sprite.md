---
title: Worm Big Body Illusion Sprite
category: entities
---

# Worm Big Body Illusion Sprite

This document details the sprite definition for the "worm_big_body_illusion" enemy in Noita, focusing on its graphical representation and animations.

## Sprite Definition

The primary sprite is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_big_body_illusion.png` - The path to the image file containing the sprite frames.
*   **offset_x**: `14` - Horizontal offset for the sprite's origin.
*   **offset_y**: `12` - Vertical offset for the sprite's origin.
*   **default_animation**: `"stand"` - The animation that plays by default when the sprite is loaded.

## Animations

The sprite utilizes `<RectAnimation>` tags to define different animation sequences.

### `stand` Animation

This animation likely represents the idle or standing state of the worm's body illusion.

#### Key Attributes:

*   **name**: `"stand"`
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `29` - The width of each individual frame.
*   **frame_height**: `26` - The height of each individual frame.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **frame_wait**: `0.082` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos_y**: `1` - The starting Y position of the animation frames within the sprite sheet.
*   **shrink_by_one_pixel**: `1` - Indicates that each frame is shrunk by one pixel, likely for visual effect or to avoid sprite bleeding.

### `eat` Animation

This animation likely represents the worm's eating animation.

#### Key Attributes:

*   **name**: `"eat"`
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `29` - The width of each individual frame.
*   **frame_height**: `26` - The height of each individual frame.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **frame_wait**: `0.082` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos_y**: `1` - The starting Y position of the animation frames within the sprite sheet.
*   **shrink_by_one_pixel**: `1` - Indicates that each frame is shrunk by one pixel.