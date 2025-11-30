---
title: Knockback Star Particle
category: guides
---

<Entity tags="particle" >
  <ParticleEmitterComponent 
    _tags="hle_particle_emitter" 
    additive_particle_color="0,0,0,255" 
    animation_randomness="0.5" 
    bounding_box_height="100" 
    bounding_box_width="100" 
    collide_with_entities="0" 
    collide_with_grid="0" 
    create_particle_on_death="1" 
    create_particle_on_update="1" 
    emitted_particle_object="data/particles/knockback_star.xml" 
    emit_cosmetic_particles="1" 
    emit_every_x_frame="1" 
    force_emit_on_update="1" 
    lifetime="0.2" 
    randomize_particle_lifetime="1" 
    randomize_particle_rotation="1" 
    randomize_particle_scale="1" 
    randomize_particle_velocity="1" 
    rotation_speed="0" 
    spawn_direction="0" 
    spawn_radius="0" 
    spawn_velocity="0" 
    sprite_file="data/particles/knockback_star.png" 
    >
  </ParticleEmitterComponent>
  <Sprite 
    default_animation="stand" 
    filename="data/particles/knockback_star.png" 
    offset_x="4.5" 
    offset_y="4.5" >
    <RectAnimation 
      name="stand" 
      frame_count="6" 
      frame_height="9" 
      frame_wait="0.08" 
      frame_width="9" 
      frames_per_row="6" 
      pos_x="0" 
      pos_y="0" 
      loop="0" >
    </RectAnimation>
  </Sprite>
</Entity>
```

---
title: Knockback Star Particle
category: particles
---

# Knockback Star Particle

This document details the configuration for the "knockback_star" particle effect in Noita, primarily used for visual feedback on knockback actions.

## Core Components

The particle is defined by an `Entity` with a `ParticleEmitterComponent` and a `Sprite` component.

### Sprite Component

This component defines the visual appearance of the particle.

*   **`filename`**: `data/particles/knockback_star.png` - The texture file used for the particle sprite.
*   **`offset_x`**, **`offset_y`**: `4.5` - Adjusts the sprite's pivot point.
*   **`default_animation`**: `"stand"` - Specifies the default animation to play.

#### RectAnimation (stand)

Defines the animation sequence for the sprite.

*   **`name`**: `"stand"` - The name of this animation.
*   **`frame_count`**: `6` - Total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: `9` - Dimensions of each individual frame.
*   **`frames_per_row`**: `6` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.08` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that the animation does not loop.

### ParticleEmitterComponent

This component controls how and when particles are generated.

*   **`emitted_particle_object`**: `data/particles/knockback_star.xml` - References the entity definition for the particles to be emitted.
*   **`sprite_file`**: `data/particles/knockback_star.png` - The sprite texture for emitted particles.
*   **`emit_every_x_frame`**: `1` - The particle emitter will attempt to emit a particle every frame.
*   **`lifetime`**: `0.2` - The duration (in seconds) each emitted particle will exist.
*   **`create_particle_on_update`**: `1` - Ensures particles are emitted continuously as long as the emitter is active.
*   **`force_emit_on_update`**: `1` - Forces emission even if other conditions aren't met.
*   **`randomize_particle_lifetime`**: `1` - Adds variation to the lifetime of emitted particles.
*   **`randomize_particle_rotation`**: `1` - Adds variation to the initial rotation of emitted particles.
*   **`randomize_particle_scale`**: `1` - Adds variation to the initial scale of emitted particles.
*   **`randomize_particle_velocity`**: `1` - Adds variation to the initial velocity of emitted particles.
*   **`additive_particle_color`**: `0,0,0,255` - Specifies the color for additive blending (black in this case, often used for glow effects).
*   **`bounding_box_width`**, **`bounding_box_height`**: `100` - Defines the area within which particles are emitted.
*   **`collide_with_entities`**, **`collide_with_grid`**: `0` - Particles do not interact with game entities or the grid.