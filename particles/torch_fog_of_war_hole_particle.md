---
title: Torch Fog of War Hole Particle
category: particles
---

# Torch Fog of War Hole Particle

This particle effect is used to create a "hole" in the fog of war, simulating the light cast by a torch.

## Sprite

The `Sprite` element defines the visual appearance of the particle.

### Key Attributes:

*   `default_animation`: Specifies the default animation to play. In this case, it's "explosion".
*   `filename`: The texture file used for the sprite.
*   `offset_x`, `offset_y`: Adjusts the position of the sprite relative to its origin.

### RectAnimation

The `RectAnimation` element defines the animation sequence for the sprite.

#### Key Attributes:

*   `frame_count`: The total number of frames in the animation.
*   `frame_height`, `frame_width`: Dimensions of each individual frame.
*   `frame_wait`: The time in seconds to wait between frames.
*   `frames_per_row`: How many frames are arranged horizontally in the texture.
*   `loop`: Whether the animation should loop (1 for true, 0 for false).
*   `name`: The name of the animation, referenced by `default_animation`.
*   `shrink_by_one_pixel`: A flag to indicate if the sprite should shrink by one pixel per frame.

```xml
<Sprite 
  default_animation="explosion" 
  filename="data/particles/explosion_flare_fog_of_war_hole.png" 
  offset_x="16" 
  offset_y="16" >

  <RectAnimation 
    frame_count="3" 
    frame_height="33" 
    frame_wait="0.02" 
    frame_width="33" 
    frames_per_row="3" 
    loop="1" 
    name="explosion" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```