---
title: Experimental Wand 1 Sprite
category: entities
---

---

# Experimental Wand 1 Sprite

This document describes the sprite data for the "experimental_wand_1" item in Noita.

## Sprite Definition

The primary sprite definition for this wand is as follows:

```xml
<Sprite filename="data/entities/items/wands/experimental/experimental_wand_1.png">
```

This indicates that the visual asset for this wand is located at the specified file path.

## RectAnimation: Default

The `RectAnimation` element defines how the sprite is rendered and animated. For the "default" animation state:

```xml
<RectAnimation
    name="default"
    pos_x="0"
    pos_y="0"
    offset_x="3"
    offset_y="4"
    has_offset="1"
    frame_count="1"
    frame_width="14"
    frame_height="8"
    frame_wait="0.2"
    frames_per_row="10"
    loop="0">
</RectAnimation>
```

**Key Attributes:**

*   **`name`**: "default" - The name of this animation state.
*   **`pos_x`, `pos_y`**: "0", "0" - The starting position of the sprite frame within the texture atlas.
*   **`offset_x`, `offset_y`**: "3", "4" - An offset applied to the sprite's position during rendering.
*   **`has_offset`**: "1" - Indicates that the `offset_x` and `offset_y` attributes are active.
*   **`frame_count`**: "1" - The total number of frames in this animation. In this case, it's a static sprite.
*   **`frame_width`, `frame_height`**: "14", "8" - The dimensions of a single frame in pixels.
*   **`frame_wait`**: "0.2" - The duration (in seconds) each frame is displayed. Since `frame_count` is 1, this value is less critical for animation but might influence initial display.
*   **`frames_per_row`**: "10" - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: "0" - Specifies whether the animation should loop. "0" means it does not loop.