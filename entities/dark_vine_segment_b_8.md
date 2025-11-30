---
title: Dark Vine Segment B (8)
category: entities
---

# Dark Vine Segment B (8)

This document describes the `vine_dark_b_8.xml` entity, which represents a segment of a dark vine in Noita.

## Sprite

The sprite for this vine segment uses the `vine_b.png` texture.

```xml
<Sprite
 filename="data/entities/verlet_chains/vines/vine_parts/vine_b.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >
```

### Animation: `stand`

This is the primary animation for the vine segment.

```xml
<RectAnimation
 name="stand"
 pos_x="28"
 pos_y="0"
 frame_count="1"
 frame_width="4"
 frame_height="3"
 frame_wait="1"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

**Key Animation Attributes:**

*   `pos_x`: The X-coordinate of the sprite frame within the texture.
*   `pos_y`: The Y-coordinate of the sprite frame within the texture.
*   `frame_width`: The width of a single animation frame.
*   `frame_height`: The height of a single animation frame.
*   `frame_count`: The total number of frames in the animation.
*   `frames_per_row`: How many frames are arranged horizontally in the texture.