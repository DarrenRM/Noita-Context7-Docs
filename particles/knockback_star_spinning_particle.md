---
title: Knockback Star Spinning Particle
category: guides
---

<Entity tags="particle" >

  <Sprite 
    default_animation="stand" 
    filename="data/particles/knockback_star_spinning.png" 
    offset_x="8" 
    offset_y="18" >

    <RectAnimation 
      name="stand" 
      frame_count="6" 
      frame_height="10" 
      frame_wait="0.06" 
      frame_width="16" 
      frames_per_row="6" 
      pos_x="0" 
      pos_y="0" 
      loop="1"
      >
    </RectAnimation>
  </Sprite>

  <Particle 
    anim_name="stand" 
    frame_delay="0.06" 
    lifetime="1" 
    particle_name="knockback_star_spinning" 
    rand_angle="360" 
    rand_force_x="0" 
    rand_force_y="0" 
    rand_rot="0" 
    rand_speed="0" 
    speed_x="0" 
    speed_y="0" 
    >
  </Particle>

  <ParticleEmitter 
    add_random_offset="1" 
    angle_min="0" 
    angle_max="360" 
    avoid_force="0" 
    burst_count="1" 
    child_entity="data/entities/particles/knockback_star_spinning_child.xml" 
    count="1" 
    delay="0.05" 
    emit_cosmetic_only="1" 
    emission_type="burst" 
    force_x="0" 
    force_y="0" 
    lifetime="0" 
    offset_x="0" 
    offset_y="0" 
    randomize_rotation="1" 
    randomize_speed="1" 
    rotation_speed="0" 
    scale_min="1" 
    scale_max="1" 
    speed_min="0" 
    speed_max="0" 
    >
  </ParticleEmitter>

  <Lifetime 
    lifetime="1" >
  </Lifetime>

  <Damage 
    amount="0" 
    damage_type="none" >
  </Damage>

  <Velocity 
    x="0" 
    y="0" >
  </Velocity>

</Entity>
```

---
title: Knockback Star Spinning Particle
category: particles
---

# Knockback Star Spinning Particle

This document describes the `knockback_star_spinning.xml` particle entity in Noita, used for visual effects.

## Sprite

The `Sprite` component defines the visual appearance of the particle.

### Key Attributes:

*   **`filename`**: `data/particles/knockback_star_spinning.png` - The texture file used for the sprite.
*   **`offset_x`**: `8` - Horizontal offset for the sprite.
*   **`offset_y`**: `18` - Vertical offset for the sprite.

#### `RectAnimation` (stand)

*   **`name`**: `stand` - The name of the animation.
*   **`frame_count`**: `6` - Total number of frames in the animation.
*   **`frame_width`**: `16` - Width of each frame.
*   **`frame_height`**: `10` - Height of each frame.
*   **`frames_per_row`**: `6` - Number of frames in each row of the sprite sheet.
*   **`frame_wait`**: `0.06` - Time in seconds each frame is displayed.
*   **`loop`**: `1` - Indicates the animation loops.

## Particle

The `Particle` component defines the behavior and properties of individual particles.

### Key Attributes:

*   **`anim_name`**: `stand` - The animation to use for the particle.
*   **`lifetime`**: `1` - The duration in seconds each particle exists.
*   **`particle_name`**: `knockback_star_spinning` - Internal name for the particle type.
*   **`speed_x`, `speed_y`**: `0` - Initial horizontal and vertical speed.
*   **`rand_speed`**: `0` - Random variation added to speed.
*   **`rand_angle`**: `360` - Random variation added to the particle's angle.

## ParticleEmitter

The `ParticleEmitter` component is responsible for spawning particles.

### Key Attributes:

*   **`child_entity`**: `data/entities/particles/knockback_star_spinning_child.xml` - The entity to spawn as a child particle.
*   **`count`**: `1` - Number of particles to emit in a burst.
*   **`delay`**: `0.05` - Delay between emissions.
*   **`emission_type`**: `burst` - How particles are emitted.
*   **`emit_cosmetic_only`**: `1` - Indicates particles are purely cosmetic.
*   **`scale_min`, `scale_max`**: `1` - Minimum and maximum scale of emitted particles.

## Lifetime

*   **`lifetime`**: `1` - The total duration this entity (and its spawned particles) will exist.

## Damage

*   **`amount`**: `0` - The damage dealt by this particle.
*   **`damage_type`**: `none` - The type of damage.

## Velocity

*   **`x`, `y`**: `0` - The initial velocity of the entity.