---
title: Rubber Ball Projectile Graphics
category: projectiles_gfx
---

# Rubber Ball Projectile Graphics

This document details the graphical assets for the "rubber_ball" projectile in Noita.

## Sprite Definition

The primary sprite definition for the rubber ball is as follows:

```xml
<Sprite
 filename="data/projectiles_gfx/rubber_ball.png"
 offset_x="2"
 offset_y="2"
 default_animation="fireball" >
</Sprite>
```

### Key Attributes:

*   **filename**: Specifies the texture file used for the projectile.
*   **offset\_x**, **offset\_y**: Define the pixel offset of the sprite from its origin.
*   **default\_animation**: Sets the initial animation to play when the projectile is spawned.

## Animation: `fireball`

The `fireball` animation defines how the sprite cycles through its frames to create movement.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="2"
 frame_width="4"
 frame_height="4"
 frame_wait="0.09"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

### Key Attributes:

*   **name**: The identifier for this animation.
*   **pos\_x**, **pos\_y**: The top-left corner of the animation frame within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual animation frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Indicates if the animation should repeat (1 for true, 0 for false).