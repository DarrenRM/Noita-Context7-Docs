---
title: Spider Nest Sprite and Animation
category: data/buildings_gfx
---

# Spider Nest Sprite and Animation

This document describes the sprite and animation data for the Spider Nest building in Noita.

## Sprite Definition

The primary sprite for the Spider Nest is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/buildings_gfx/spidernest.png` - Specifies the image file containing the sprite.
*   **offset_x**: `16` - Horizontal offset for the sprite's origin.
*   **offset_y**: `32` - Vertical offset for the sprite's origin.
*   **default_animation**: `stand` - The animation to play by default when the sprite is active.

## Animation Definition

The Spider Nest has a single defined animation named "stand".

### Key Attributes:

*   **name**: `stand` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `4` - The total number of frames in this animation.
*   **frame_width**: `32` - The width of each individual animation frame.
*   **frame_height**: `32` - The height of each individual animation frame.
*   **frame_wait**: `0.15` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet for this animation.
*   **loop**: `1` - Indicates that the animation should loop indefinitely (1 for true, 0 for false).

```xml
<Sprite
 filename="data/buildings_gfx/spidernest.png"
 offset_x="16"
 offset_y="32"
 default_animation="stand" >

 <!-- animation -->
 <RectAnimation
  name="stand"
  pos_x="0"
  pos_y="0"
  frame_count="4"
  frame_width="32"
  frame_height="32"
  frame_wait="0.15"
  frames_per_row="4"
  loop="1"   >
 </RectAnimation>
</Sprite>
```