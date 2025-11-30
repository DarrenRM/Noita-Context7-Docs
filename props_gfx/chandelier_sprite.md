---
title: Chandelier Sprite
category: props_gfx
---

# Chandelier Sprite

This documentation describes the sprite definition for the chandelier prop in Noita.

## Sprite Definition

The primary sprite for the chandelier is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/props_gfx/chandelier.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8.5` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `18` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default when the sprite is active.

## Animations

The chandelier sprite utilizes two identical animations: "stand" and "out". These animations define how the sprite is rendered.

### Animation Details (for both "stand" and "out")

*   **name**: `"stand"` / `"out"` - The name of the animation.
*   **pos\_x**: `"0"` - The starting X position within the sprite sheet for this animation.
*   **pos\_y**: `"0"` - The starting Y position within the sprite sheet for this animation.
*   **frame\_count**: `"1"` - The total number of frames in this animation.
*   **frame\_width**: `"17"` - The width of each individual frame.
*   **frame\_height**: `"19"` - The height of each individual frame.
*   **frame\_wait**: `"0.1"` - The time in seconds to wait between frames.
*   **frames\_per\_row**: `"1"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates whether the animation should loop (1 for true, 0 for false).

```xml
<Sprite
 filename="data/props_gfx/chandelier.png"
 offset_x="8.5"
 offset_y="18" 
 default_animation="stand">

 <!-- stand -->
 <RectAnimation
  name="stand"
  pos_x="0"
  pos_y="0"
  frame_count="1"
  frame_width="17"
  frame_height="19"
  frame_wait="0.1"
  frames_per_row="1"
  loop="1"   >
 </RectAnimation>
 
 <RectAnimation
  name="out"
  pos_x="0"
  pos_y="0"
  frame_count="1"
  frame_width="17"
  frame_height="19"
  frame_wait="0.1"
  frames_per_row="1"
  loop="1"   >
 </RectAnimation>
 
</Sprite>
```