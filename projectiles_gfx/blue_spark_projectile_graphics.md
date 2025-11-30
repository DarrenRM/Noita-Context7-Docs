---
title: Blue Spark Projectile Graphics
category: projectiles_gfx
---

# Blue Spark Projectile Graphics

This document describes the graphical assets for the "blue spark" projectile in Noita, as defined in `spark_blue.xml`.

## Sprite Definition

The primary sprite for the blue spark projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/spark_blue.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `4.5` - Horizontal offset for the sprite's anchor point.
*   **offset\_y**: `4.5` - Vertical offset for the sprite's anchor point.

## Animation: Default

The projectile utilizes a rectangular animation for its visual effect.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **frame\_count**: `2` - The total number of frames in the animation.
*   **frame\_width**: `10` - The width of each individual animation frame.
*   **frame\_height**: `10` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally within the sprite sheet.
*   **pos\_x**: `0` - The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: `1` - The starting Y-coordinate of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates that each frame should shrink by one pixel, likely for a fading or shrinking effect.

```xml
<Sprite 
  filename="data/projectiles_gfx/spark_blue.png" 
  offset_x="4.5" 
  offset_y="4.5" >

  <RectAnimation 
    frame_count="2" 
    frame_height="10" 
    frame_wait="0.2" 
    frame_width="10" 
    frames_per_row="10" 
    name="default" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```