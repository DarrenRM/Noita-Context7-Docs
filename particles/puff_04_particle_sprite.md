---
title: Puff 04 Particle Sprite
category: particles
---

# Puff 04 Particle Sprite

This document describes the sprite and animation data for the `puff_04` particle effect in Noita.

## Sprite Data

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/particles/puff_04.png` - Specifies the image file used for the particle's visual representation.
*   **offset\_x**: `3` - Horizontal offset for the sprite.
*   **offset\_y**: `3` - Vertical offset for the sprite.

## Animation Data

The particle utilizes a rectangular animation named "explosion".

### Key Attributes:

*   **name**: `explosion` - The identifier for this animation.
*   **frame\_count**: `3` - The total number of frames in the animation.
*   **frame\_width**: `7` - The width of each individual frame in pixels.
*   **frame\_height**: `7` - The height of each individual frame in pixels.
*   **frames\_per\_row**: `3` - How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.19` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **loop**: `0` - Indicates that the animation does not loop (it plays once).
*   **shrink\_by\_one\_pixel**: `1` - Suggests that each frame might shrink by one pixel per animation cycle, contributing to a fading or shrinking effect.
*   **pos\_x**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `1` - The starting Y position of the animation frames within the sprite sheet.

```xml
<Sprite 
  default_animation="explosion" 
  filename="data/particles/puff_04.png" 
  offset_x="3" 
  offset_y="3" >

  <RectAnimation 
    frame_count="3" 
    frame_height="7" 
    frame_wait="0.19" 
    frame_width="7" 
    frames_per_row="3" 
    loop="0" 
    name="explosion" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```