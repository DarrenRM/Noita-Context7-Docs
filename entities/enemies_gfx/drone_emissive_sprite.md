---
title: Drone Emissive Sprite
category: entities/enemies_gfx
---

# Drone Emissive Sprite

This document describes the sprite data for the "drone_emissive" enemy in Noita, focusing on its graphical representation and animation.

## Sprite Definition

The primary sprite definition for the drone emissive is as follows:

```xml
<Sprite
filename="data/enemies_gfx/drone_emissive.png"
offset_x="12"
offset_y="7"
  default_animation="stand" >
</Sprite>
```

### Key Attributes:

*   **filename**: Specifies the image file used for the sprite (`data/enemies_gfx/drone_emissive.png`).
*   **offset\_x**: Horizontal offset of the sprite's origin.
*   **offset\_y**: Vertical offset of the sprite's origin.
*   **default\_animation**: The animation that plays by default when the sprite is active.

## Animations

The drone emissive sprite utilizes a single defined animation: "stand".

### Stand Animation

This animation defines the visual sequence for the drone's standing state.

```xml
<RectAnimation
name="stand"
pos_x="0"
pos_y="0"
frame_count="5"
frame_width="24"
frame_height="16"
frame_wait="0.1"
frames_per_row="5"
loop="1"   >
</RectAnimation>
```

#### Key Attributes:

*   **name**: The identifier for this animation ("stand").
*   **pos\_x**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in this animation (5).
*   **frame\_width**: The width of each individual animation frame (24 pixels).
*   **frame\_height**: The height of each individual animation frame (16 pixels).
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next (0.1 seconds).
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet for this animation (5).
*   **loop**: Indicates if the animation should loop (1 for true, 0 for false).