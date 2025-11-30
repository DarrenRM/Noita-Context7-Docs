---
title: Small Red Slimeball Projectile Graphics
category: projectiles_gfx
---

---

# Small Red Slimeball Projectile Graphics

This document details the graphical assets for the "small red slimeball" projectile in Noita, as defined in `slimeball_small_red.xml`.

## Sprite Definition

The primary sprite definition for this projectile is as follows:

```xml
<Sprite
 filename="data/projectiles_gfx/slimeball_small_red.png"
 offset_x="6"
 offset_y="6"
 default_animation="spawn" >
```

**Key Attributes:**

*   **`filename`**: Specifies the texture file used for the projectile's graphics.
*   **`offset_x`**, **`offset_y`**: Define the sprite's pivot point relative to its center.
*   **`default_animation`**: Sets the animation to play when the projectile is first created.

## Animations

The projectile utilizes two distinct animations: `spawn` and `fireball`.

### Spawn Animation

This animation plays upon the projectile's creation, likely a brief visual effect before it becomes active.

```xml
<RectAnimation
 name="spawn"
 pos_x="0"
 pos_y="12"
 frame_count="4"
 frame_width="12"
 frame_height="12"
 frame_wait="0.02"
 frames_per_row="4"
 next_animation="fireball"
 loop="0" >
</RectAnimation>
```

**Key Attributes:**

*   **`name`**: Identifies this animation as "spawn".
*   **`pos_x`**, **`pos_y`**: Define the starting coordinates of the animation frames within the sprite sheet.
*   **`frame_count`**: The total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`next_animation`**: Specifies the animation to transition to after this one completes.
*   **`loop`**: Indicates if the animation should repeat (`1` for loop, `0` for no loop).

### Fireball Animation

This is the primary animation for the projectile while it is in motion.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="12"
 frame_height="12"
 frame_wait="0.10"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

**Key Attributes:**

*   **`name`**: Identifies this animation as "fireball".
*   **`pos_x`**, **`pos_y`**: Define the starting coordinates of the animation frames within the sprite sheet.
*   **`frame_count`**: The total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: Indicates if the animation should repeat (`1` for loop, `0` for no loop).