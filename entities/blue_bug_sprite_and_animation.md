---
title: Blue Bug Sprite and Animation
category: entities
---

# Blue Bug Sprite and Animation

This document describes the sprite and animation data for the "Blue Bug" entity in Noita.

## Sprite

The `Sprite` element defines the visual appearance and default animation of the entity.

```xml
<Sprite
 filename="data/entities/animals/boss_centipede/bug_blue.png"
 offset_x="13"
 offset_y="13"
 default_animation="fireball" >
</Sprite>
```

*   **filename**: Specifies the path to the sprite image file.
*   **offset\_x**, **offset\_y**: Adjust the sprite's position relative to the entity's origin.
*   **default\_animation**: Sets the animation to play by default when the entity is spawned.

## Animation: `fireball`

The `RectAnimation` element defines a specific animation sequence.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="26"
 frame_height="26"
 frame_wait="0.09"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

*   **name**: The identifier for this animation, referenced by `default_animation` or other animation controllers.
*   **pos\_x**, **pos\_y**: The top-left corner of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Determines if the animation should repeat (`1` for loop, `0` for no loop).