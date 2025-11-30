---
title: Small Muzzle Flash Particle
category: entities
---

# Small Muzzle Flash Particle

This entity defines a small muzzle flash effect, typically used for firearms. It consists of a visual sprite and a particle emitter that generates sparks.

## SpriteComponent

This component handles the visual appearance of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet for the animation. The `$[1-5]` indicates a sequence of 5 frames.
*   `rect_animation`: Defines the name of the animation sequence.
*   `next_rect_animation`: Specifies the next animation to play after the current one finishes.
*   `emissive`: Set to `1` to make the sprite emit light.
*   `additive`: Set to `1` for additive blending, making the sprite brighter when overlapping.
*   `kill_entity_after_finished`: Set to `1` to automatically remove the entity once the animation is complete.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's origin.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/particles/muzzle_flashes/muzzle_small_0$[1-5].png" 
  next_rect_animation="muzzle"
  rect_animation="muzzle"
  emissive="1"
  additive="1"
  kill_entity_after_finished="1"
  offset_x="5"
  offset_y="7"
>
</SpriteComponent>
```

## ParticleEmitterComponent

This component is responsible for generating secondary particles (sparks) that accompany the muzzle flash.

### Key Attributes:

*   `emitted_material_name`: The material of the particles to be emitted (e.g., "spark").
*   `offset.x`, `offset.y`: The offset of the emitter from the entity's origin.
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines the area where particles can be spawned.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the velocity range for the emitted particles.
*   `count_min`, `count_max`: The number of particles to emit per emission.
*   `lifetime_min`, `lifetime_max`: The duration each emitted particle will exist.
*   `create_real_particles`: Set to `0` to indicate these are cosmetic particles, not physical entities.
*   `emit_cosmetic_particles`: Set to `1` to enable the emission of cosmetic particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle emissions. Set to `0` for a single burst.
*   `is_emitting`: Set to `1` to start emitting particles immediately.

```xml
<ParticleEmitterComponent 
  emitted_material_name="spark"
  offset.x="0"
  offset.y="0"
  x_pos_offset_min="-1"
  y_pos_offset_min="-1"
  x_pos_offset_max="1"
  y_pos_offset_max="1"
  x_vel_min="300"
  x_vel_max="50"
  y_vel_min="0"
  y_vel_max="0"
  count_min="1"
  count_max="4"
  lifetime_min="0.0"
  lifetime_max="0.1"
  create_real_particles="0"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="0"
  emission_interval_max_frames="0"
  is_emitting="1" >
</ParticleEmitterComponent>
```