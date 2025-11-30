---
title: Bush Growth 4 Sprite
category: data/vegetation
---

# Bush Growth 4 Sprite

This document describes the sprite and animation data for `bush_growth_4.xml`, a vegetation asset in Noita.

## Sprite Data

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/bush_growth_4.png` - Specifies the image file for the sprite.
*   **offset\_x**: `18` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `31` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation to play by default. This is a special name that triggers a growing vegetation effect.

## Animation Data

The animation for this vegetation is defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `vegetation_growth` - The name of this animation.
*   **pos\_x**: `0` - The X position of the animation's top-left corner within the sprite sheet.
*   **pos\_y**: `0` - The Y position of the animation's top-left corner within the sprite sheet.
*   **frame\_count**: `5` - The total number of frames in the animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `34` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

```xml
<Sprite
 filename="data/vegetation/bush_growth_4.png"
 offset_x="18"
 offset_y="31"
 default_animation="vegetation_growth" >

 <!-- vegetation_growth is special name, creates a growing vegetation with it -->
 <RectAnimation
  name="vegetation_growth"
  pos_x="0"
  pos_y="0"
  frame_count="5"
  frame_width="32"
  frame_height="34"
  frame_wait="1.0"
  frames_per_row="6"
  loop="1"   >
 </RectAnimation>

</Sprite>
```