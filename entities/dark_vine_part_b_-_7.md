---
title: Dark Vine Part B - 7
category: entities
---

# Dark Vine Part B - 7

This entity defines a segment of a dark vine, specifically part 'B' and the 7th variation. It's a visual component used in Noita'sverlet chain system for creating vine-like structures.

## Sprite Information

The sprite for this vine segment is defined by the following attributes:

```xml
<Sprite
 filename="data/entities/verlet_chains/vines/vine_parts/vine_dark_b.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >
```

*   **filename**: Specifies the texture file used for the sprite.
*   **offset\_x**, **offset\_y**: Define the sprite's position relative to its entity's origin.
*   **default\_animation**: Sets the initial animation to play.

### Animation Details

The `stand` animation is configured as follows:

```xml
<RectAnimation
 name="stand"
 pos_x="24"
 pos_y="0"
 frame_count="1"
 frame_width="4"
 frame_height="3"
 frame_wait="1"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

*   **name**: The identifier for this animation.
*   **pos\_x**, **pos\_y**: The starting coordinates within the sprite sheet for this animation frame.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: The duration each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Indicates if the animation should repeat (1 for true, 0 for false).