---
title: Meatvine Part B (Vine_b_7) Sprite
category: entities
---

---

# Meatvine Part B (Vine_b_7) Sprite

This documentation describes the sprite and animation data for a specific part of the Meatvine entity in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the entity part.

```xml
<Sprite
 filename="data/entities/verlet_chains/meatvine/vine_parts/vine_b.png"
 offset_x="0"
 offset_y="0"
 default_animation="stand" >
```

*   **filename**: Specifies the texture file used for the sprite.
*   **offset\_x**, **offset\_y**: Define the sprite's pivot point relative to its entity.
*   **default\_animation**: Sets the animation to play by default when the entity is spawned.

## Animation: `stand`

The `RectAnimation` element defines a rectangular animation sequence.

```xml
<RectAnimation
 name="stand"
 pos_x="24"
 pos_y="0"
 frame_count="1"
 frame_width="4"
 frame_height="3"
 frame_wait="1"
 frames_per_row="8"
 loop="1" >
</RectAnimation>
```

*   **name**: The identifier for this animation, referenced by `default_animation` or other animation controllers.
*   **pos\_x**, **pos\_y**: The top-left corner of the sprite frame within the `filename` texture.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in game ticks) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the texture file.
*   **loop**: Indicates if the animation should loop (1 for true, 0 for false).