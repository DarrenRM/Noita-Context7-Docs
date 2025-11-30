---
title: Flower 07 Sprite and Animation
category: data/vegetation
---

---

# Flower 07 Sprite and Animation

This documentation describes the sprite and animation data for `flower_07.xml`, a vegetation entity in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation and initial positioning of the entity.

### Key Attributes:

*   **filename**: `data/vegetation/flower_07.png` - Specifies the image file used for the sprite.
*   **offset_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset_y**: `44` - The vertical offset of the sprite's origin.
*   **default_animation**: `vegetation_growth` - The name of the animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation Definition

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `vegetation_growth` - The identifier for this animation.
*   **pos_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos_y**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `32` - The width of each individual frame.
*   **frame_height**: `48` - The height of each individual frame.
*   **frame_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).

### Special Note:

The `vegetation_growth` animation name is a special keyword in Noita. When used as `default_animation`, it signifies that the entity should exhibit a growing vegetation effect.