---
title: Large Blue Blood Splatter Particle
category: particles
---

# Large Blue Blood Splatter Particle

This document describes the configuration for a large blue blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite configuration defines the visual appearance and animation of the particle.

### Sprite Attributes

| Attribute      | Description                                                                 |
| -------------- | --------------------------------------------------------------------------- |
| `default_animation` | The name of the default animation to play.                                  |
| `filename`     | The path to the sprite sheet containing the animation frames.               |
| `offset_x`     | The horizontal offset of the sprite's origin.                               |
| `offset_y`     | The vertical offset of the sprite's origin.                                 |

### RectAnimation Attributes

This element defines a rectangular animation sequence.

| Attribute        | Description                                                                 |
| ---------------- | --------------------------------------------------------------------------- |
| `frame_count`    | The total number of frames in the animation.                                |
| `frame_height`   | The height of each individual frame in pixels.                              |
| `frame_wait`     | The time in seconds to wait between each frame.                             |
| `frame_width`    | The width of each individual frame in pixels.                               |
| `frames_per_row` | The number of frames arranged horizontally in the sprite sheet.             |
| `loop`           | Whether the animation should loop (0 for no, 1 for yes).                    |
| `name`           | The internal name of this animation.                                        |
| `pos_x`          | The starting X position of the animation frames within the sprite sheet.    |
| `pos_y`          | The starting Y position of the animation frames within the sprite sheet.    |
| `shrink_by_one_pixel` | If set to 1, each frame will shrink by one pixel after each animation cycle. |

```xml
<Sprite 
  default_animation="smoke" 
  filename="data/particles/bloodsplatters/bloodsplatter_large_blue_1.png" 
  offset_x="16" 
  offset_y="16" >

  <RectAnimation 
    frame_count="6" 
    frame_height="33" 
    frame_wait="0.03" 
    frame_width="33" 
    frames_per_row="8" 
    loop="0" 
    name="smoke" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```