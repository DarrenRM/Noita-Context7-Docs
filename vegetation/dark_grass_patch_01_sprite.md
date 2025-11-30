---
title: Dark Grass Patch 01 Sprite
category: data
---

---

# Dark Grass Patch 01 Sprite

This document describes the sprite data for `grass_dark_patch_01.xml`, a vegetation element in Noita.

## Sprite Definition

The primary sprite definition for this vegetation patch is as follows:

```xml
<Sprite
 filename="data/vegetation/grass_dark_patch_01.png"
 offset_x="10"
 offset_y="9"
 default_animation="vegetation_growth" >
```

**Key Attributes:**

*   **filename**: Specifies the texture file used for the sprite (`data/vegetation/grass_dark_patch_01.png`).
*   **offset\_x**, **offset\_y**: Define the sprite's pivot point relative to its origin.
*   **default\_animation**: Sets the animation to play by default when the sprite is instantiated. In this case, it's `vegetation_growth`.

## Animation: vegetation_growth

The `vegetation_growth` animation is a special type that signifies a growing vegetation element.

```xml
<RectAnimation
 name="vegetation_growth"
 pos_x="0"
 pos_y="0"
 frame_count="1"
 frame_width="20"
 frame_height="10"
 frame_wait="1.0"
 frames_per_row="1"
 loop="1" >
</RectAnimation>
```

**Key Attributes:**

*   **name**: Identifies the animation as `vegetation_growth`.
*   **frame\_count**: The total number of frames in the animation (1 in this case, indicating a static sprite for the growth phase).
*   **frame\_width**, **frame\_height**: Dimensions of each frame in pixels.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the texture.
*   **loop**: Determines if the animation should loop (1 for true, 0 for false).