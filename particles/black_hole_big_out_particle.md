---
title: Black Hole Big Out Particle
category: guides
---

<Entity tags="hittable,particle" name="black_hole_big_out">
  <ParticleEmitter 
    angle_max="360" 
    angle_min="0" 
    blend_mode="add" 
    color_change_speed="0" 
    color_end="0,0,0,0" 
    color_start="255,255,255,255" 
    count_max="100" 
    count_min="50" 
    damage_scale="0" 
    depth_max="0" 
    depth_min="0" 
    gravity_x="0" 
    gravity_y="0" 
    lifetime_max="0.5" 
    lifetime_min="0.2" 
    offset_x="0" 
    offset_y="0" 
    radius_max="15" 
    radius_min="5" 
    rotation_speed="0" 
    scale_max="1" 
    scale_min="0.5" 
    speed_max="50" 
    speed_min="10" 
    sprite_file="data/particles/black_hole_big_out.png" 
    sprite_offset_x="48" 
    sprite_offset_y="48" 
    use_gravity="0" >
  </ParticleEmitter>
  <ParticleEmitter 
    angle_max="360" 
    angle_min="0" 
    blend_mode="add" 
    color_change_speed="0" 
    color_end="0,0,0,0" 
    color_start="255,255,255,255" 
    count_max="50" 
    count_min="25" 
    damage_scale="0" 
    depth_max="0" 
    depth_min="0" 
    gravity_x="0" 
    gravity_y="0" 
    lifetime_max="0.3" 
    lifetime_min="0.1" 
    offset_x="0" 
    offset_y="0" 
    radius_max="10" 
    radius_min="2" 
    rotation_speed="0" 
    scale_max="0.5" 
    scale_min="0.2" 
    speed_max="70" 
    speed_min="20" 
    sprite_file="data/particles/black_hole_big_out.png" 
    sprite_offset_x="48" 
    sprite_offset_y="48" 
    use_gravity="0" >
  </ParticleEmitter>
  <Sprite 
    default_animation="explosion" 
    filename="data/particles/black_hole_big_out.png" 
    offset_x="48" 
    offset_y="48" >
    <RectAnimation 
      frame_count="7" 
      frame_height="97" 
      frame_wait="0.03" 
      frame_width="97" 
      frames_per_row="7" 
      loop="0" 
      name="explosion" 
      pos_x="0" 
      pos_y="1" 
      shrink_by_one_pixel="1" >
    </RectAnimation>
  </Sprite>
  <Lifetime 
    lifetime="0.2" >
  </Lifetime>
  <Explosion 
    damage="0" 
    explosion_radius="20" 
    explosion_type="damage" 
    push_force="100" >
  </Explosion>
  <Damage 
    amount="0" 
    instakill_on_touch="0" >
  </Damage>
  <Velocity 
    x="0" 
    y="0" >
  </Velocity>
</Entity>
```

---
title: Black Hole Big Out Particle
category: particles
---

# Black Hole Big Out Particle

This document describes the `black_hole_big_out.xml` entity, which represents a particle effect in Noita. This particle is designed to simulate the visual and physical effects of a large black hole's outward expulsion.

## Key Components

The `black_hole_big_out` entity is composed of several key components that define its behavior and appearance:

### Sprite

The `Sprite` component defines the visual representation of the particle.

*   **`filename`**: `data/particles/black_hole_big_out.png` - Specifies the texture file used for the particle.
*   **`offset_x`**, **`offset_y`**: `48` - These values define the center of the sprite's origin.
*   **`default_animation`**: `"explosion"` - Sets the default animation to be played.

#### RectAnimation: `explosion`

This nested element defines the animation sequence for the sprite.

*   **`name`**: `"explosion"` - The name of this animation.
*   **`frame_count`**: `7` - The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: `97` - The dimensions of each individual frame.
*   **`frames_per_row`**: `7` - Indicates how many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.03` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: `0` - This animation does not loop.
*   **`shrink_by_one_pixel`**: `1` - Suggests a visual effect where the sprite might appear to shrink slightly.

### ParticleEmitter

This entity utilizes two `ParticleEmitter` components to generate multiple smaller particles, creating a more complex visual effect.

#### ParticleEmitter 1

*   **`blend_mode`**: `"add"` - Particles are added to the scene, often resulting in brighter effects.
*   **`color_start`**: `"255,255,255,255"` - Particles begin as white with full opacity.
*   **`color_end`**: `"0,0,0,0"` - Particles fade to transparent black.
*   **`count_min`**, **`count_max`**: `50` to `100` - The number of particles emitted.
*   **`lifetime_min`**, **`lifetime_max`**: `0.2` to `0.5` seconds - The duration each emitted particle exists.
*   **`speed_min`**, **`speed_max`**: `10` to `50` - The initial velocity of the emitted particles.
*   **`scale_min`**, **`scale_max`**: `0.5` to `1` - The size range of the emitted particles.
*   **`radius_min`**, **`radius_max`**: `5` to `15` - The area from which particles are emitted.
*   **`angle_min`**, **`angle_max`**: `0` to `360` - Particles are emitted in all directions.
*   **`sprite_file`**: `data/particles/black_hole_big_out.png` - The sprite used for the emitted particles.

#### ParticleEmitter 2

This emitter generates a denser, faster, and shorter-lived set of particles.

*   **`count_min`**, **`count_max`**: `25` to `50`
*   **`lifetime_min`**, **`lifetime_max`**: `0.1` to `0.3` seconds
*   **`speed_min`**, **`speed_max`**: `20` to `70`
*   **`scale_min`**, **`scale_max`**: `0.2` to `0.5`
*   **`radius_min`**, **`radius_max`**: `2` to `10`

### Lifetime

*   **`lifetime`**: `0.2` - The main `black_hole_big_out` entity itself exists for 0.2 seconds.

### Explosion

*   **`push_force`**: `100` - The force that pushes entities away from the center of the explosion.
*   **`explosion_radius`**: `20` - The area of effect for the push force.
*   **`explosion_type`**: `"damage"` - While the damage amount is 0, this tag might influence how other game systems interact with it.

### Damage

*   **`amount`**: `0` - This particle does not inflict direct damage.

### Velocity

*   **`x`**, **`y`**: `0` - The entity has no inherent velocity. Its movement is dictated by other forces or its creation context.

## Usage

This particle is likely used to signify the end of a powerful black hole spell or effect, creating a visual burst of energy and a outward push. The combination of a fading sprite animation and multiple particle emitters creates a dynamic and impactful visual.