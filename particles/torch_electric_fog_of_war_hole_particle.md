---
title: Torch Electric Fog of War Hole Particle
category: guides
---

<Entity tags="torch, particle" name="torch_electric_fog_of_war_hole">
  <ParticleEmitter 
    add_every_x_frames="1" 
    animation_speed="1" 
    attach_to_entity="1" 
    bone_name="chip_emitter_center" 
    camera_distance_fade_end="1000" 
    camera_distance_fade_start="500" 
    circle_radius="0" 
    count="1" 
    delay="0" 
    depth_bias="0" 
    fade_out_time="0.5" 
    gravity_y="0" 
    is_emitting="1" 
    lifetime="0.5" 
    randomize_rotation="0" 
    randomize_velocity="0" 
    rotation_speed="0" 
    set_world_position="1" 
    spawn_cone_angle="0" 
    spawn_cone_radius="0" 
    sprite="data/particles/torch_electric_fog_of_war_hole.png" 
    target_entity="1" 
    use_rotation="0" 
    velocity_x="0" 
    velocity_y="0" >
  </ParticleEmitter>
  <Sprite 
    default_animation="idle" 
    filename="data/particles/torch_electric_fog_of_war_hole.png" 
    offset_x="24.5" 
    offset_y="24.5" >
    <RectAnimation 
      frame_count="1" 
      frame_height="49" 
      frame_wait="1" 
      frame_width="49" 
      frames_per_row="1" 
      loop="1" 
      name="idle" 
      pos_x="0" 
      pos_y="0" >
    </RectAnimation>
  </Sprite>
</Entity>
```

---
title: Torch Electric Fog of War Hole Particle
category: particles
---

# Torch Electric Fog of War Hole Particle

This entity defines a particle effect used to create a "fog of war" hole, likely for visual effects related to electrical torches or similar entities.

## Key Components

### Sprite
This defines the visual appearance of the particle.

| Attribute        | Value      | Description                                                                 |
| :--------------- | :--------- | :-------------------------------------------------------------------------- |
| `filename`       | `data/particles/torch_electric_fog_of_war_hole.png` | The image file used for the particle's sprite. |
| `offset_x`       | `24.5`     | Horizontal offset for the sprite's origin.                                  |
| `offset_y`       | `24.5`     | Vertical offset for the sprite's origin.                                    |

#### RectAnimation (idle)
Defines the animation for the sprite.

| Attribute        | Value | Description                                                                 |
| :--------------- | :---- | :-------------------------------------------------------------------------- |
| `frame_count`    | `1`   | Number of frames in the animation.                                          |
| `frame_height`   | `49`  | Height of each frame in pixels.                                             |
| `frame_wait`     | `1`   | Time in seconds to wait between frames.                                     |
| `frame_width`    | `49`  | Width of each frame in pixels.                                              |
| `frames_per_row` | `1`   | Number of frames arranged horizontally in the sprite sheet.                 |
| `loop`           | `1`   | Whether the animation should loop (1 for true, 0 for false).                |
| `name`           | `idle`| The name of this animation state.                                           |

### ParticleEmitter
This component is responsible for spawning and managing the particles.

| Attribute              | Value | Description                                                                 |
| :--------------------- | :---- | :-------------------------------------------------------------------------- |
| `add_every_x_frames`   | `1`   | How often (in frames) to add new particles.                                 |
| `attach_to_entity`     | `1`   | Whether the emitter should be attached to the entity it's part of.          |
| `bone_name`            | `chip_emitter_center` | The specific bone on the parent entity to attach the emitter to. |
| `camera_distance_fade_end` | `1000`| Distance at which the particles fully fade out.                             |
| `camera_distance_fade_start`| `500` | Distance at which particles begin to fade out.                              |
| `count`                | `1`   | Number of particles to spawn per emission.                                  |
| `fade_out_time`        | `0.5` | Duration in seconds for particles to fade out.                              |
| `lifetime`             | `0.5` | Duration in seconds each particle exists.                                   |
| `sprite`               | `data/particles/torch_electric_fog_of_war_hole.png` | The sprite to use for the spawned particles. |
| `set_world_position`   | `1`   | Whether to set the particle's position in world space.                      |

## Entity Tags

*   `torch`
*   `particle`

These tags help categorize the entity and define its behavior within the game.