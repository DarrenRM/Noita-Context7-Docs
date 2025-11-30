---
title: Huge Red Slimeball Projectile Sprite
category: projectiles_gfx
---

# Huge Red Slimeball Projectile Sprite

This document describes the sprite data for the "Huge Red Slimeball" projectile in Noita. It details the visual assets and animations used to render this projectile in-game.

## Sprite Definition

The primary sprite definition for the projectile is as follows:

```xml
<Sprite
 filename="data/projectiles_gfx/slimeball_huge_red.png"
 offset_x="15"
 offset_y="15"
 default_animation="spawn" >
```

### Key Attributes:

*   **filename**: Specifies the texture file containing the projectile's visual data.
*   **offset\_x**, **offset\_y**: Define the sprite's pivot point relative to its center.
*   **default\_animation**: Sets the animation to play when the projectile is first created.

## Animations

The projectile utilizes two distinct animations: `spawn` and `fireball`.

### `spawn` Animation

This animation plays when the projectile is initially spawned, likely a brief visual effect.

```xml
<RectAnimation
 name="spawn"
 pos_x="0"
 pos_y="30"
 frame_count="4"
 frame_width="30"
 frame_height="30"
 frame_wait="0.02"
 frames_per_row="4"
 next_animation="fireball"
 loop="0" >
</RectAnimation>
```

#### Key Attributes:

*   **name**: The identifier for this animation.
*   **pos\_x**, **pos\_y**: The starting coordinates within the `filename` texture for this animation's frames.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the texture.
*   **next\_animation**: Specifies the animation to transition to after this one completes.
*   **loop**: Indicates if the animation should loop (`1` for true, `0` for false).

### `fireball` Animation

This animation likely represents the projectile's main visual state while in motion.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="30"
 frame_height="30"
 frame_wait="0.10"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

#### Key Attributes:

*   **name**: The identifier for this animation.
*   **pos\_x**, **pos\_y**: The starting coordinates within the `filename` texture for this animation's frames.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the texture.
*   **loop**: Indicates if the animation should loop (`1` for true, `0` for false).