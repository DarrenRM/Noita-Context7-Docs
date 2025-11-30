---
title: Wooden Board 64x4 Sprite
category: building
---

---

# Wooden Board 64x4 Sprite

This document describes the sprite data for a wooden board entity in Noita, specifically a 64x4 pixel variant.

## Sprite Definition

The primary sprite definition for this entity is as follows:

```xml
<Sprite
 filename="data/temp/building/wooden_board64.png"
 offset_x="32"
 offset_y="2" >
```

### Key Attributes:

*   **filename**: Specifies the texture file used for the sprite.
*   **offset\_x**: The horizontal offset of the sprite's origin.
*   **offset\_y**: The vertical offset of the sprite's origin.

## Animation Data

The sprite includes a single animation state named "default".

```xml
 <RectAnimation
  name="default"
  pos_x="0"
  pos_y="0"
  frame_count="1"
  frame_width="64"
  frame_height="4"
  frame_wait="0.12"
  frames_per_row="6"
  loop="1" >
 </RectAnimation>
```

### Key Attributes:

*   **name**: The name of the animation state.
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: Indicates if the animation should loop (1 for true, 0 for false).

This animation defines a static, single-frame sprite representing the wooden board.