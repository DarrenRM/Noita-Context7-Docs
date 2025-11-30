---
title: Meatvine Segment A5 Sprite
category: entities
---

# Meatvine Segment A5 Sprite

This document describes the sprite and animation data for a segment of the Meatvine entity in Noita.

## Sprite

The sprite defines the visual appearance and basic positioning of the entity segment.

```xml
<Sprite
 filename="data/entities/verlet_chains/meatvine/vine_parts/vine_a.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >
```

*   **filename**: Specifies the texture file used for the sprite.
*   **offset\_x**, **offset\_y**: Define the sprite's origin point relative to the entity's center.
*   **default\_animation**: Sets the animation to play when the entity is first loaded.

## Animation: stand

This section details the "stand" animation, which is the default animation for this sprite.

```xml
<RectAnimation
 name="stand"
 pos_x="16"
 pos_y="0"
 frame_count="1"
 frame_width="4"
 frame_height="3"
 frame_wait="1"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

*   **name**: The identifier for this animation.
*   **pos\_x**, **pos\_y**: The starting coordinates within the sprite sheet for the animation frames.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Indicates if the animation should repeat (1 for true, 0 for false).