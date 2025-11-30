---
title: Medium Magic Muzzle Flash
category: entities/particles
---

# Medium Magic Muzzle Flash

This entity defines a visual effect for a medium-sized magic muzzle flash in Noita. It utilizes sprite animations and particle emitters to create a dynamic and visually appealing flash.

## SpriteComponent

This component handles the visual representation of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet used for the animation. It uses a pattern `muzzle_magic_medium_0$[1-5].png` indicating frames 1 through 5.
*   `next_rect_animation`: Defines the animation state to transition to after the current one finishes. Set to "muzzle".
*   `rect_animation`: Defines the current animation state. Set to "muzzle".
*   `emissive`: Set to "1", meaning the sprite emits light.
*   `additive`: Set to "1", indicating additive blending for the sprite, which is common for light effects.
*   `kill_entity_after_finished`: Set to "1", meaning the entity will be destroyed once the sprite animation is complete.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's origin.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/particles/muzzle_flashes/muzzle_magic_medium_0$[1-5].png" 
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

## ParticleEmitterComponent (Spark Emitter)

This component emits small, short-lived "spark" particles.

### Key Attributes:

*   `emitted_material_name`: The material of the particles to emit. Set to "spark_blue".
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Define a small area around the emitter where particles can spawn.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Define the velocity range for the emitted particles. In this case, particles are primarily shot outwards horizontally with some variation.
*   `count_min`, `count_max`: The number of particles to emit per emission.
*   `lifetime_min`, `lifetime_max`: The duration each particle will exist. Very short here (0.0 to 0.1 seconds).
*   `create_real_particles`: Set to "0", meaning these are cosmetic particles, not physical entities.
*   `emit_cosmetic_particles`: Set to "1", confirming these are cosmetic.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Set to "0", meaning particles are emitted instantly.
*   `is_emitting`: Set to "1", enabling the emitter.

```xml
<ParticleEmitterComponent 
  emitted_material_name="spark_blue"
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
  count_max="6"
  lifetime_min="0.0"
  lifetime_max="0.1"
  create_real_particles="0"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="0"
  emission_interval_max_frames="0"
  is_emitting="1" >
</ParticleEmitterComponent>
```

## ParticleEmitterComponent (Plasma Emitter)

This component emits "plasma fading" particles, which are longer-lived and have different movement characteristics.

### Key Attributes:

*   `emitted_material_name`: The material of the particles to emit. Set to "plasma_fading".
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Set to "0", meaning particles spawn directly at the emitter's origin.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Define the velocity range. Particles have a moderate horizontal velocity and a slight vertical spread.
*   `count_min`, `count_max`: The number of particles to emit per emission.
*   `lifetime_min`, `lifetime_max`: The duration each particle will exist. Longer than the sparks (1.0 to 4.1 seconds).
*   `fade_based_on_lifetime`: Set to "1", meaning particles will fade out as their lifetime progresses.
*   `render_on_grid`: Set to "1", indicating these particles should be rendered on the game grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These attributes suggest the particles are affected by airflow, adding a subtle drift.
*   `create_real_particles`: Set to "0", cosmetic particles.
*   `emit_cosmetic_particles`: Set to "1", cosmetic particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Defines a delay between emissions (2 to 8 frames), creating a pulsating effect.
*   `is_emitting`: Set to "1", enabling the emitter.

```xml
<ParticleEmitterComponent 
  emitted_material_name="plasma_fading"
  offset.x="0"
  offset.y="0"
  gravity.y="0"
  x_pos_offset_min="0"
  y_pos_offset_min="0"
  x_pos_offset_max="0"
  y_pos_offset_max="0"
  x_vel_min="20"
  x_vel_max="45"
  y_vel_min="-2"
  y_vel_max="2"
  count_min="1"
  count_max="2"
  lifetime_min="1.0"
  lifetime_max="4.1"
  fade_based_on_lifetime="1"
  render_on_grid="1"
  airflow_force="0.5"
  airflow_time="0.5"
  airflow_scale="0.05"
  create_real_particles="0"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="2"
  emission_interval_max_frames="8"
  is_emitting="1" >
</ParticleEmitterComponent>
```