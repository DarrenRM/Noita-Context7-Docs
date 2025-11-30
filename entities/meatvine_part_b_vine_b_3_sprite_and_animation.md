---
title: Meatvine Part B (Vine_b_3) Sprite and Animation
category: entities
---

# Meatvine Part B (Vine_b_3) Sprite and Animation

This document details the sprite and animation configuration for `vine_b_3.xml`, a part of the meatvine entity in Noita.

## Sprite Configuration

The `Sprite` element defines the visual appearance and default animation for this entity part.

```xml
<Sprite
 filename="data/entities/verlet_chains/meatvine/vine_parts/vine_b.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >
```

*   **`filename`**: Specifies the texture file used for the sprite.
*   **`offset_x`**, **`offset_y`**: Define the sprite's pivot point relative to its entity.
*   **`default_animation`**: Sets the animation to play by default when the entity is spawned.

## Animation: `stand`

The `RectAnimation` element defines the "stand" animation.

```xml
 <RectAnimation
  name="stand"
  pos_x="8"
  pos_y="0"
  frame_count="1"
  frame_width="4"
  frame_height="3"
  frame_wait="1"
  frames_per_row="8"
  loop="1"   >
 </RectAnimation>
```

*   **`name`**: The identifier for this animation.
*   **`pos_x`**, **`pos_y`**: The starting position of the animation frames within the sprite sheet.
*   **`frame_count`**: The total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual animation frame.
*   **`frame_wait`**: The duration (in game ticks) each frame is displayed before advancing.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: Indicates if the animation should repeat (`1` for true, `0` for false).