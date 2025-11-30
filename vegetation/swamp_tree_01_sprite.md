---
title: Swamp Tree 01 Sprite
category: data/vegetation
---

# Swamp Tree 01 Sprite

This document describes the sprite and animation data for `swamp_tree_01.xml`, a vegetation asset in Noita.

## Sprite Definition

The primary sprite for this vegetation is defined by the `<Sprite>` tag.

```xml
<Sprite
 filename="data/vegetation/swamp_tree_01.png"
 offset_x="32"
 offset_y="175" 
 default_animation="vegetation_growth" >
</Sprite>
```

### Key Sprite Attributes:

*   **filename**: Specifies the texture file used for the sprite (`data/vegetation/swamp_tree_01.png`).
*   **offset\_x**: The horizontal offset of the sprite's origin.
*   **offset\_y**: The vertical offset of the sprite's origin.
*   **default\_animation**: The name of the animation that plays by default when the sprite is instantiated.

## Animation: `vegetation_growth`

The `vegetation_growth` animation is a special type of animation in Noita that signifies a growing vegetation entity.

```xml
<RectAnimation
 name="vegetation_growth"
 pos_x="0"
 pos_y="0"
 frame_count="1"
 frame_width="64"
 frame_height="180"
 frame_wait="1.0"
 frames_per_row="1"
 loop="1"   >
</RectAnimation>
```

### Key Animation Attributes:

*   **name**: Identifies the animation as `vegetation_growth`.
*   **frame\_count**: The total number of frames in the animation (1 in this case, indicating a static sprite or the start of a growth sequence).
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: Indicates if the animation should loop (1 for true, 0 for false).