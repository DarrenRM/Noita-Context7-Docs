---
title: Mimic Potion Sprite
category: entities
---

# Mimic Potion Sprite

This documentation describes the sprite data for the Mimic Potion enemy in Noita.

## Sprite Attributes

The primary sprite for the Mimic Potion is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/mimic_potion.png` - The path to the sprite image file.
*   **offset_x**: `5` - Horizontal offset for the sprite.
*   **offset_y**: `4` - Vertical offset for the sprite.
*   **default_animation**: `stand` - The animation to play by default.

## Animations

The sprite includes a single animation named "stand".

### `stand` Animation Details:

*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_height**: `8` - The height of each individual frame.
*   **frame_wait**: `0.082` - The time in seconds to wait between frames.
*   **frame_width**: `9` - The width of each individual frame.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **name**: `stand` - The name of this animation.
*   **pos_x**: `0` - The X-coordinate of the top-left corner of the animation's frame within the sprite sheet.
*   **pos_y**: `0` - The Y-coordinate of the top-left corner of the animation's frame within the sprite sheet.

```xml
<Sprite 
  filename="data/enemies_gfx/mimic_potion.png" 
  offset_x="5" 
  offset_y="4" 
  default_animation="stand">

  <RectAnimation 
    frame_count="1" 
    frame_height="8" 
    frame_wait="0.082" 
    frame_width="9" 
    frames_per_row="1" 
    name="stand" 
    pos_x="0" 
    pos_y="0" 
    >

  </RectAnimation>

</Sprite>
```