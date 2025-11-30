---
title: Dark Vine Part A (5)
category: entities
---

# Dark Vine Part A (5)

This entity defines a single segment of a dark blue vine. It's a visual component used in the construction of larger vine structures.

## Sprite

The sprite defines the visual appearance of the vine segment.

```xml
<Sprite
 filename="data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_a.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >
```

### Animation: `stand`

This defines the animation for the vine segment.

```xml
<RectAnimation
 name="stand"
 pos_x="16"
 pos_y="0"
 frame_count="1"
 frame_width="4"
 frame_height="3"
 frame_wait="1"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

**Key Attributes:**

*   `filename`: Path to the sprite sheet.
*   `default_animation`: The animation to play by default.
*   `pos_x`, `pos_y`: The starting position of the animation frame within the sprite sheet.
*   `frame_width`, `frame_height`: Dimensions of a single animation frame.
*   `frame_count`: Total number of frames in the animation.
*   `frames_per_row`: How many frames are in a single row of the sprite sheet.
*   `loop`: Whether the animation should loop (1 for yes, 0 for no).