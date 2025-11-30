---
title: Spark 03 Particle
category: particles
---

---

# Spark 03 Particle

This document describes the `spark_03.xml` particle definition, used for a specific type of spark effect in Noita.

## Sprite Definition

The primary sprite for this particle is defined as follows:

```xml
<Sprite
filename="data/particles/spark_03.png"
offset_x="8"
offset_y="8"
default_animation="explosion"
>
</Sprite>
```

### Key Sprite Attributes:

*   **filename**: Specifies the image file used for the sprite (`data/particles/spark_03.png`).
*   **offset\_x**, **offset\_y**: Define the sprite's origin point within its texture.
*   **default\_animation**: Sets the initial animation to play when the particle is created (`explosion`).

## Animation: Explosion

The `explosion` animation defines how the sprite changes over time.

```xml
<RectAnimation
name="explosion"
pos_x="0"
pos_y="0"
frame_count="3"
frame_width="16"
frame_height="16"
frame_wait="0.03"
frames_per_row="3"
loop="0"
>
</RectAnimation>
```

### Key Animation Attributes:

*   **name**: Identifies this animation as `explosion`.
*   **frame\_count**: The total number of frames in the animation (3).
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame (16x16 pixels).
*   **frame\_wait**: The duration each frame is displayed before advancing (0.03 seconds).
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet (3).
*   **loop**: Determines if the animation repeats. `0` indicates it does not loop.