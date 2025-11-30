---
title: Blood Splatter Directional Orange 3 Particle
category: particles
---

# Blood Splatter Directional Orange 3 Particle

This document describes the configuration for a directional orange blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual component of this particle is defined by its sprite.

### Sprite Attributes

| Attribute   | Value                                         | Description                                                                 |
| :---------- | :-------------------------------------------- | :-------------------------------------------------------------------------- |
| `filename`  | `data/particles/bloodsplatters/bloodsplatter_directional_orange_3.png` | The image file used for the particle's visual representation.               |
| `offset_x`  | `8`                                           | Horizontal offset of the sprite's origin.                                   |
| `offset_y`  | `8`                                           | Vertical offset of the sprite's origin.                                     |
| `default_animation` | `smoke`                                       | The name of the default animation to play when the particle is spawned.     |

## Animation Configuration

This section details the animation sequence for the blood splatter.

### RectAnimation: `smoke`

This animation defines how the sprite frames are sequenced to create the visual effect.

| Attribute        | Value   | Description                                                                                                |
| :--------------- | :------ | :--------------------------------------------------------------------------------------------------------- |
| `name`           | `smoke` | The identifier for this animation, referenced by `default_animation` in the `Sprite` tag.                  |
| `pos_x`          | `0`     | Starting X position within the sprite sheet for the animation frames.                                      |
| `pos_y`          | `0`     | Starting Y position within the sprite sheet for the animation frames.                                      |
| `frame_count`    | `5`     | The total number of frames in this animation sequence.                                                     |
| `frame_width`    | `32`    | The width of each individual frame in pixels.                                                              |
| `frame_height`   | `16`    | The height of each individual frame in pixels.                                                             |
| `frame_wait`     | `0.025` | The duration (in seconds) each frame is displayed before transitioning to the next.                        |
| `frames_per_row` | `8`     | The number of frames that fit horizontally within a single row of the sprite sheet.                        |
| `loop`           | `0`     | Indicates whether the animation should loop. `0` means it will not loop (play once).                       |

```xml
<Sprite
filename="data/particles/bloodsplatters/bloodsplatter_directional_orange_3.png"
offset_x="8"
offset_y="8"
default_animation="smoke"
 >

<!-- explosion -->
<RectAnimation
name="smoke"
pos_x="0"
pos_y="0"
frame_count="5"
frame_width="32"
frame_height="16"
frame_wait="0.025"
frames_per_row="8"
loop="0"   >
</RectAnimation>
</Sprite>
```