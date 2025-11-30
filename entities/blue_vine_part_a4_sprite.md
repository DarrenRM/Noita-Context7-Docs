---
title: Blue Vine Part A4 Sprite
category: entities
---

# Blue Vine Part A4 Sprite

This documentation describes the sprite configuration for a specific part of a blue vine entity in Noita.

## Sprite Configuration

The `<Sprite>` element defines the visual appearance of the entity.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/vines/vine_parts_blue/vine_a.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite.
*   **offset\_y**: `0` - Vertical offset of the sprite.
*   **default\_animation**: `stand` - The animation that plays by default when the entity is active.

### Animation: `stand`

The `<RectAnimation>` element defines the animation details.

#### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos\_x**: `12` - The X-coordinate of the top-left corner of the sprite frame within the texture.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the sprite frame within the texture.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `4` - The width of each individual animation frame.
*   **frame\_height**: `3` - The height of each individual animation frame.
*   **frame\_wait**: `1` - The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: `8` - The number of frames arranged horizontally in the texture file.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

```xml
<Sprite
 filename="data/entities/verlet_chains/vines/vine_parts_blue/vine_a.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >

 <!-- animation -->
 <RectAnimation
  name="stand"
  pos_x="12"
  pos_y="0"
  frame_count="1"
  frame_width="4"
  frame_height="3"
  frame_wait="1"
  frames_per_row="8"
  loop="1"   >
 </RectAnimation>
</Sprite>
```