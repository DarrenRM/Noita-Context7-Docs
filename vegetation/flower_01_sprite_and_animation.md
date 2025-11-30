---
title: Flower 01 Sprite and Animation
category: data/vegetation
---

# Flower 01 Sprite and Animation

This document describes the sprite and animation data for `flower_01.xml`, a common vegetation element in Noita.

## Sprite Information

The primary sprite for `flower_01` is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/vegetation/flower_01.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `16` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `44` - The vertical offset of the sprite's origin.
*   **default\_animation**: `vegetation_growth` - The name of the animation that plays by default when this sprite is used.

## Animation Data

The `vegetation_growth` animation is a special type of animation in Noita that signifies a growing vegetation element.

### `vegetation_growth` Animation Details:

*   **name**: `vegetation_growth`
*   **pos\_x**: `0` - The X position of the animation's starting frame within the sprite sheet.
*   **pos\_y**: `0` - The Y position of the animation's starting frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `32` - The width of each individual frame.
*   **frame\_height**: `48` - The height of each individual frame.
*   **frame\_wait**: `1.0` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

```xml
<Sprite
 filename="data/vegetation/flower_01.png"
 offset_x="16"
 offset_y="44" 
 default_animation="vegetation_growth" >

 <!-- vegetation_growth is special name, creates a growing vegetation with it -->
 <RectAnimation
  name="vegetation_growth"
  pos_x="0"
  pos_y="0"
  frame_count="1"
  frame_width="32"
  frame_height="48"
  frame_wait="1.0"
  frames_per_row="1"
  loop="1"   >
 </RectAnimation>

</Sprite>
```