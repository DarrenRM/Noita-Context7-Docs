---
title: Dark Blue Vine Part B (6)
category: entities
---

# Dark Blue Vine Part B (6)

This entity defines a segment of a dark blue vine. It's a visual component for a verlet chain, likely used for creating dynamic, growing vine structures.

## Sprite Information

The sprite defines the visual appearance of the vine segment.

```xml
<Sprite
 filename="data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_b.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >
```

*   **filename**: Specifies the texture file for the sprite.
*   **offset\_x**, **offset\_y**: Define the sprite's position relative to its entity's origin.
*   **default\_animation**: Sets the initial animation to play.

### Animation Details

The `stand` animation defines how the sprite is rendered.

```xml
<RectAnimation
 name="stand"
 pos_x="20"
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
*   **pos\_x**, **pos\_y**: The starting coordinates within the sprite sheet for this animation.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: Delay between frames (in game ticks).
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop (1 for yes, 0 for no).