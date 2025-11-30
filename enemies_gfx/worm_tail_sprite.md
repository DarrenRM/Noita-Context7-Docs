---
title: Worm Tail Sprite
category: guides
---

<Sprite 
  filename="data/enemies_gfx/worm_tail.png" 
  offset_x="15" 
  offset_y="6" 
  default_animation="stand">

  <RectAnimation 
    frame_count="1" 
    frame_height="12" 
    frame_wait="0.082" 
    frame_width="14" 
    frames_per_row="1" 
    name="stand" 
    pos_x="0" 
    pos_y="0" 
    >

  </RectAnimation>

</Sprite>
```

---
title: Worm Tail Sprite
category: entities
---

# Worm Tail Sprite

This document describes the sprite definition for the worm tail enemy in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the worm tail.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_tail.png` - The path to the sprite image file.
*   **offset\_x**: `15` - Horizontal offset for the sprite.
*   **offset\_y**: `6` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The `<RectAnimation>` tag defines individual animations.

### `stand` Animation:

*   **name**: `"stand"` - The name of this animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `14` - The width of each frame.
*   **frame\_height**: `12` - The height of each frame.
*   **frames\_per\_row**: `1` - The number of frames in each row of the sprite sheet.
*   **frame\_wait**: `0.082` - The time in seconds to wait between frames.
*   **pos\_x**: `0` - The X-coordinate of the top-left corner of the animation's frame(s) within the sprite sheet.
*   **pos\_y**: `0` - The Y-coordinate of the top-left corner of the animation's frame(s) within the sprite sheet.