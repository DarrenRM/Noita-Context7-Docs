---
title: Dark Vine Part A (Blue)
category: entities
---

# Dark Vine Part A (Blue)

This entity defines a single segment of a dark blue vine, used in Noita's Verlet chains.

## Sprite Information

The sprite for this vine segment is defined by the following:

```xml
<Sprite
 filename="data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_a.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >
```

### Animation Details

The `stand` animation is used for this vine segment:

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

*   **`frame_width`**: 4 pixels
*   **`frame_height`**: 3 pixels
*   **`frame_count`**: 1 (This is a static sprite, not animated in the traditional sense)
*   **`frames_per_row`**: 8 (Indicates the sprite sheet layout)