---
title: Cyst Sprite Animation
category: props_gfx
---

# Cyst Sprite Animation

This documentation describes the sprite animation for the "cyst" prop in Noita, focusing on its visual representation and animation properties.

## Sprite Definition

The primary sprite definition for the cyst is as follows:

```xml
<Sprite
 filename="data/props_gfx/cyst.png"
 offset_x="9"
 offset_y="11" 
 default_animation="grow" >
```

### Key Attributes:

*   **filename**: Specifies the texture file used for the sprite (`data/props_gfx/cyst.png`).
*   **offset\_x**: The horizontal offset of the sprite's origin.
*   **offset\_y**: The vertical offset of the sprite's origin.
*   **default\_animation**: The name of the animation that plays by default when the sprite is initialized (`grow`).

## Animation: "grow"

The "grow" animation defines how the cyst sprite animates.

```xml
 <RectAnimation
  name="grow"
  pos_x="0"
  pos_y="0"
  frame_count="5"
  frame_width="18"
  frame_height="18"
  frame_wait="0.07"
  frames_per_row="8"
  loop="1"   >
 </RectAnimation>
```

### Key Attributes:

*   **name**: The identifier for this animation (`grow`).
*   **pos\_x**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in this animation (5 frames).
*   **frame\_width**: The width of each individual animation frame (18 pixels).
*   **frame\_height**: The height of each individual animation frame (18 pixels).
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next (0.07 seconds).
*   **frames\_per\_row**: The number of frames that fit horizontally in a single row of the sprite sheet (8 frames). This is crucial for calculating frame positions.
*   **loop**: Indicates if the animation should loop. `1` means it will loop indefinitely.