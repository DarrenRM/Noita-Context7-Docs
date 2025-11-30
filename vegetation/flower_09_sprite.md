---
title: Flower 09 Sprite
category: data
---

---

# Flower 09 Sprite

This documentation describes the sprite and animation data for `flower_09.xml`, a vegetation asset in Noita.

## Sprite Definition

The primary sprite definition for this vegetation is as follows:

```xml
<Sprite
 filename="data/vegetation/flower_09.png"
 offset_x="16"
 offset_y="44" 
 default_animation="vegetation_growth" >
</Sprite>
```

### Key Attributes:

*   **filename**: Specifies the texture file used for the sprite (`data/vegetation/flower_09.png`).
*   **offset_x**: The horizontal offset of the sprite's origin.
*   **offset_y**: The vertical offset of the sprite's origin.
*   **default_animation**: The name of the animation that plays by default when this sprite is used. In this case, it's `vegetation_growth`.

## Animation: `vegetation_growth`

This animation is a special type used for vegetation that grows over time.

```xml
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
```

### Key Attributes:

*   **name**: The identifier for this animation (`vegetation_growth`).
*   **frame_count**: The total number of frames in the animation (1).
*   **frame_width**: The width of each individual frame (32 pixels).
*   **frame_height**: The height of each individual frame (48 pixels).
*   **frame_wait**: The duration (in seconds) each frame is displayed before advancing (1.0 second).
*   **frames_per_row**: The number of frames arranged horizontally in the sprite sheet (1).
*   **loop**: Indicates if the animation should loop (1 for true, 0 for false).