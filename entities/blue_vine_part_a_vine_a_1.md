---
title: Blue Vine Part A (Vine A 1)
category: entities
---

# Blue Vine Part A (Vine A 1)

This entity defines a single segment of a blue vine, specifically the "vine_a_1" variant. It's a visual component for averlet chain, likely used to construct larger vine structures.

## Sprite Information

The visual representation of this vine segment is handled by a `Sprite` component.

```xml
<Sprite
filename="data/entities/verlet_chains/vines/vine_parts_blue/vine_a.png"
offset_x="0"
offset_y="0"
default_animation="stand" >
```

*   **filename**: Specifies the texture file used for the sprite.
*   **offset\_x**, **offset\_y**: Define the sprite's origin point.
*   **default\_animation**: Sets the initial animation to play.

### Animation Details

The `stand` animation is a simple, non-looping animation for this vine segment.

```xml
<RectAnimation
    name="stand"
    pos_x="0"
    pos_y="0"
    frame_count="1"
    frame_width="4"
    frame_height="3"
    frame_wait="1"
    frames_per_row="8"
    loop="1" >
</RectAnimation>
```

*   **name**: The name of the animation.
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: Delay between frames.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop (1 for yes, 0 for no).