---
title: Minecart Sprite and Animation
category: props_gfx
---

# Minecart Sprite and Animation

This document describes the sprite and animation data for the minecart prop in Noita.

## Sprite Definition

The primary sprite definition for the minecart is as follows:

```xml
<Sprite
 filename="data/props_gfx/minecart.png"
 offset_x="9"
 offset_y="7.5" 
 default_animation="minecart">
</Sprite>
```

### Key Attributes:

*   **filename**: Specifies the texture file used for the minecart sprite.
*   **offset\_x**: Horizontal offset for the sprite's origin.
*   **offset\_y**: Vertical offset for the sprite's origin.
*   **default\_animation**: The name of the animation to play by default.

## Animations

### Minecart Animation

This section details the "minecart" animation, which is the default animation for the minecart.

```xml
<RectAnimation
 name="minecart"
 pos_x="0"
 pos_y="0"
 frame_count="1"
 frame_width="18"
 frame_height="15"
 frame_wait="0.23"
 frames_per_row="1"
 loop="1">
</RectAnimation>
```

#### Key Attributes:

*   **name**: The identifier for this animation.
*   **pos\_x**, **pos\_y**: The top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual animation frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Determines if the animation should loop (1 for true, 0 for false).