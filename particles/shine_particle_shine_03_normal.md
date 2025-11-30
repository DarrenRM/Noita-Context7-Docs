---
title: Shine Particle (shine_03_normal)
category: particles
---

# Shine Particle (shine_03_normal)

This documentation describes the `shine_03_normal.xml` file, which defines a specific particle effect in Noita. This particle is a small, shimmering light effect.

## Sprite Definition

The primary sprite definition for this particle is as follows:

```xml
<Sprite
filename="data/particles/shine_03.png"
offset_x="4.5"
offset_y="4.5"
default_animation="explosion"
>
```

### Key Attributes:

*   **filename**: Specifies the image file used for the particle sprite (`data/particles/shine_03.png`).
*   **offset\_x**, **offset\_y**: Define the offset of the sprite's origin from its center.
*   **default\_animation**: Sets the default animation to be played when the particle is spawned.

## Animation: Explosion

The `shine_03_normal` particle uses a `RectAnimation` named "explosion" to define its visual sequence.

```xml
<!-- explosion -->
<RectAnimation
name="explosion"
pos_x="0"
pos_y="0"
frame_count="4"
frame_width="9"
frame_height="9"
frame_wait="0.03"
frames_per_row="4"
loop="1"
>
</RectAnimation>
```

### Key Attributes:

*   **name**: Identifies this animation as "explosion".
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation (4 frames).
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame (9x9 pixels).
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing to the next (0.03 seconds).
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet (4 frames per row).
*   **loop**: Indicates if the animation should loop (1 for true, meaning it will loop indefinitely).