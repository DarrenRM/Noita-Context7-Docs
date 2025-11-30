---
title: Spark Particle 01
category: particles
---

# Spark Particle 01

This documentation describes the `spark_01.xml` file, which defines a basic spark particle effect in Noita.

## Sprite Definition

The primary element is `<Sprite>`, which defines the visual appearance and animation of the particle.

### Key Attributes

| Attribute     | Description                                                              |
|---------------|--------------------------------------------------------------------------|
| `filename`    | Path to the sprite sheet containing the particle's frames.               |
| `offset_x`    | Horizontal offset for the sprite's origin.                               |
| `offset_y`    | Vertical offset for the sprite's origin.                                 |
| `default_animation` | The name of the animation to play by default.                        |

## Animation Definition

The `<RectAnimation>` element defines how the sprite sheet is used to create an animation.

### Key Attributes

| Attribute       | Description                                                              |
|-----------------|--------------------------------------------------------------------------|
| `name`          | The name of this animation, referenced by `default_animation`.           |
| `pos_x`         | Starting X position of the animation frames within the sprite sheet.     |
| `pos_y`         | Starting Y position of the animation frames within the sprite sheet.     |
| `frame_count`   | The total number of frames in the animation.                             |
| `frame_width`   | The width of each individual frame.                                      |
| `frame_height`  | The height of each individual frame.                                     |
| `frame_wait`    | The duration (in seconds) each frame is displayed before advancing.      |
| `frames_per_row`| The number of frames arranged horizontally in the sprite sheet.          |
| `loop`          | Whether the animation should loop (1 for loop, 0 for no loop).           |

### Animation Frames (Explosion)

This specific animation, named "explosion", consists of 3 frames, each 16x16 pixels. It plays once without looping.

```xml
<!-- explosion -->
<RectAnimation
name="explosion"
pos_x="0"
pos_y="0"
frame_count="3"
frame_width="16"
frame_height="16"
frame_wait="0.03"
frames_per_row="3"
loop="0"   >
</RectAnimation>
```