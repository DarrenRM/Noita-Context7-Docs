---
title: Slime Explosion Particle
category: particles
---

# Slime Explosion Particle

This document describes the configuration for a slime-themed explosion particle effect in Noita, as defined in `explosion_032_slime.xml`.

## Sprite Configuration

The particle utilizes a sprite sheet for its visual representation.

### Sprite Attributes

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `filename`    | Path to the sprite sheet image.                 |
| `offset_x`    | Horizontal offset for the sprite.               |
| `offset_y`    | Vertical offset for the sprite.                 |
| `default_animation` | The name of the default animation to play. |

```xml
<Sprite
filename="data/particles/explosion_032_slime.png"
offset_x="16"
offset_y="16"
default_animation="explosion"
>
```

## Animation Configuration

The particle features a single animation named "explosion".

### Animation Attributes

| Attribute       | Description                                                              |
|-----------------|--------------------------------------------------------------------------|
| `name`          | The identifier for this animation.                                       |
| `pos_x`         | Starting X position of the animation frames within the sprite sheet.     |
| `pos_y`         | Starting Y position of the animation frames within the sprite sheet.     |
| `frame_count`   | The total number of frames in the animation.                             |
| `frame_width`   | The width of each individual frame.                                      |
| `frame_height`  | The height of each individual frame.                                     |
| `frame_wait`    | The time in seconds to wait between each frame.                          |
| `frames_per_row`| The number of frames arranged horizontally in the sprite sheet.          |
| `loop`          | Determines if the animation should loop (0 for no loop, 1 for loop). |

```xml
<RectAnimation
name="explosion"
pos_x="0"
pos_y="0"
frame_count="9"
frame_width="32"
frame_height="32"
frame_wait="0.021"
frames_per_row="8"
loop="0"
>
</RectAnimation>
```