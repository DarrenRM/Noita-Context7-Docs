---
title: Yellow Slimeball Projectile Graphics
category: projectiles_gfx
---

# Yellow Slimeball Projectile Graphics

This document details the graphical assets for the yellow slimeball projectile in Noita, as defined in `slimeball_yellow.xml`.

## Sprite Definition

The primary sprite definition for the yellow slimeball.

```xml
<Sprite
 filename="data/projectiles_gfx/slimeball_yellow.png"
 offset_x="12"
 offset_y="12"
 default_animation="spawn" >
```

### Key Attributes:

*   **filename**: Specifies the texture file used for the projectile's graphics.
*   **offset\_x**, **offset\_y**: Defines the pivot point or center of the sprite.
*   **default\_animation**: Sets the initial animation to play when the projectile is created.

## Animations

The yellow slimeball utilizes two distinct animations: `spawn` and `fireball`.

### Spawn Animation

This animation plays when the projectile is first created, likely a brief visual effect.

```xml
<RectAnimation
 name="spawn"
 pos_x="0"
 pos_y="24"
 frame_count="4"
 frame_width="24"
 frame_height="24"
 frame_wait="0.02"
 frames_per_row="4"
 next_animation="fireball"
 loop="0" >
</RectAnimation>
```

#### Key Attributes:

*   **name**: Identifies this animation as "spawn".
*   **pos\_x**, **pos\_y**: The starting coordinates within the sprite sheet for this animation.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **next\_animation**: Specifies the animation to transition to after this one completes.
*   **loop**: Indicates if the animation should loop (0 for no, 1 for yes).

### Fireball Animation

This animation likely represents the projectile in its active flight state.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="24"
 frame_height="24"
 frame_wait="0.10"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

#### Key Attributes:

*   **name**: Identifies this animation as "fireball".
*   **pos\_x**, **pos\_y**: The starting coordinates within the sprite sheet for this animation.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Indicates if the animation should loop (0 for no, 1 for yes).