---
title: Ghostly Hanging Torch Flame Sprite
category: props_gfx
---

---

# Ghostly Hanging Torch Flame Sprite

This document describes the sprite data for the ghostly hanging torch flame in Noita.

## Sprite Definition

The main sprite definition points to the image file and sets the default animation.

```xml
<Sprite
 filename="data/props_gfx/torch_hang_flame_ghostly.png"
 offset_x="6"
 offset_y="18" 
 default_animation="default">
```

*   **filename**: Specifies the path to the sprite image.
*   **offset\_x**: Horizontal offset for the sprite.
*   **offset\_y**: Vertical offset for the sprite.
*   **default\_animation**: The animation to play by default.

## Animations

### `default` Animation

This animation represents the standard, flickering state of the ghostly torch flame.

```xml
<RectAnimation
 name="default"
 pos_x="0"
 pos_y="0"
 frame_count="8"
 frame_width="12"
 frame_height="19"
 frame_wait="0.1"
 frames_per_row="8"
 loop="1">
</RectAnimation>
```

*   **name**: Identifier for the animation.
*   **pos\_x**, **pos\_y**: Starting position of the animation frames within the sprite sheet.
*   **frame\_count**: Total number of frames in this animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: Time in seconds between frames.
*   **frames\_per\_row**: Number of frames arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop (1 for yes, 0 for no).

### `out` Animation

This animation likely represents the flame being extinguished or in a transition state.

```xml
<RectAnimation
 name="out"
 pos_x="0"
 pos_y="19"
 frame_count="1"
 frame_width="12"
 frame_height="19"
 frame_wait="0.1"
 frames_per_row="4"
 loop="1">
</RectAnimation>
```

*   **name**: Identifier for the animation.
*   **pos\_x**, **pos\_y**: Starting position of the animation frames within the sprite sheet. Note that `pos_y` is offset from the `default` animation, indicating these frames are on a different row.
*   **frame\_count**: Total number of frames in this animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: Time in seconds between frames.
*   **frames\_per\_row**: Number of frames arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop.