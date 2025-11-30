---
title: Worm Body Sprite
category: guides
---

<Sprite 
  filename="data/enemies_gfx/worm_body.png" 
  offset_x="15" 
  offset_y="6"
  default_animation="stand" >

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
title: Worm Body Sprite
category: entities/gfx
---

# Worm Body Sprite

This document describes the sprite definition for the worm body enemy in Noita.

## Sprite Definition

The main `<Sprite>` tag defines the visual representation of the worm body.

### Key Attributes

*   **filename**: Specifies the path to the sprite image file.
    *   `data/enemies_gfx/worm_body.png`
*   **offset\_x**: Horizontal offset for the sprite.
    *   `15`
*   **offset\_y**: Vertical offset for the sprite.
    *   `6`
*   **default\_animation**: The animation to play by default.
    *   `stand`

## Animations

The `<RectAnimation>` tag defines individual animations.

### `stand` Animation

This is the primary animation for the worm body.

#### Key Attributes

*   **name**: The name of the animation.
    *   `stand`
*   **frame\_count**: The total number of frames in the animation.
    *   `1`
*   **frame\_width**: The width of each frame.
    *   `14`
*   **frame\_height**: The height of each frame.
    *   `12`
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
    *   `1`
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
    *   `0.082`
*   **pos\_x**: The starting X-coordinate of the animation frames within the sprite sheet.
    *   `0`
*   **pos\_y**: The starting Y-coordinate of the animation frames within the sprite sheet.
    *   `0`