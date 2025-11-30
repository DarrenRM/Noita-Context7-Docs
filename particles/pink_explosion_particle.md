---
title: Pink Explosion Particle
category: particles
---

# Pink Explosion Particle

This document describes the configuration for a pink explosion particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite configuration defines the visual appearance and animation of the particle.

### Key Attributes

| Attribute       | Description                                                                 |
| --------------- | --------------------------------------------------------------------------- |
| `filename`      | Path to the sprite sheet containing the particle's frames.                  |
| `offset_x`      | Horizontal offset for the sprite's origin.                                  |
| `offset_y`      | Vertical offset for the sprite's origin.                                    |

### Animations

This particle utilizes two `RectAnimation` elements to define its visual sequence.

#### `explosion` Animation

This animation defines the forward playback of the explosion frames.

| Attribute         | Description                                                                 |
| ----------------- | --------------------------------------------------------------------------- |
| `name`            | The name of this animation, referenced by the `default_animation` attribute. |
| `frame_count`     | Total number of frames in this animation.                                   |
| `frame_width`     | Width of each individual frame.                                             |
| `frame_height`    | Height of each individual frame.                                            |
| `frames_per_row`  | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`      | Time in seconds to display each frame.                                      |
| `loop`            | Whether the animation should loop (0 for no loop, 1 for loop).              |
| `pos_x`           | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`           | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | Whether to shrink each frame by one pixel after each use.                   |

#### `reverse` Animation

This animation defines the reverse playback of the explosion frames, likely for a fading or retracting effect.

| Attribute         | Description                                                                 |
| ----------------- | --------------------------------------------------------------------------- |
| `name`            | The name of this animation.                                                 |
| `frame_count`     | Total number of frames in this animation.                                   |
| `frame_width`     | Width of each individual frame.                                             |
| `frame_height`    | Height of each individual frame.                                            |
| `frames_per_row`  | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`      | Time in seconds to display each frame.                                      |
| `loop`            | Whether the animation should loop (0 for no loop, 1 for loop).              |
| `pos_x`           | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`           | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | Whether to shrink each frame by one pixel after each use.                   |

```xml
<Sprite 
  default_animation="explosion" 
  filename="data/particles/explosion_100_pink.png" 
  offset_x="50" 
  offset_y="50" >

  <RectAnimation 
    frame_count="5" 
    frame_height="101" 
    frame_wait="0.03" 
    frame_width="101" 
    frames_per_row="5" 
    loop="0" 
    name="explosion" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

  <RectAnimation 
    frame_count="5" 
    frame_height="101" 
    frame_wait="0.03" 
    frame_width="101" 
    frames_per_row="5" 
    loop="0" 
    name="reverse" 
    pos_x="0" 
    pos_y="102" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```