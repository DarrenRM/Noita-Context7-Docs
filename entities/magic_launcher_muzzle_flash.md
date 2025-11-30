---
title: Magic Launcher Muzzle Flash
category: entities
---

# Magic Launcher Muzzle Flash

This entity defines the visual effect of a muzzle flash for a magic launcher weapon in Noita. It primarily uses sprite animations and particle emitters to create a dynamic and visually appealing flash.

## Sprite Component

This component handles the visual representation of the muzzle flash itself.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet used for the animation. It uses a pattern `muzzle_magic_launcher_0$[1-5].png` indicating multiple frames.
*   `rect_animation`: Defines the name of the animation sequence to use from the sprite sheet.
*   `next_rect_animation`: Similar to `rect_animation`, likely for controlling animation flow.
*   `emissive`: Set to `1`, meaning the sprite emits light.
*   `additive`: Set to `1`, indicating additive blending for the sprite, making it appear brighter when overlapping.
*   `kill_entity_after_finished`: Set to `1`, meaning the muzzle flash entity will be destroyed once its animation is complete.
*   `offset_x`, `offset_y`: Adjusts the position of the sprite relative to the entity's origin.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/particles/muzzle_flashes/muzzle_magic_launcher_0$[1-5].png" 
  next_rect_animation="muzzle"
  rect_animation="muzzle"
  emissive="1"
  additive="1"
  kill_entity_after_finished="1"
  offset_x="7"
  offset_y="9"
>
</SpriteComponent>
```

## Particle Emitter Components

This entity utilizes two `ParticleEmitterComponent`s to generate additional visual effects, such as sparks.

### Particle Emitter 1 (Short-lived sparks)

This emitter creates a quick burst of green sparks immediately upon firing.

#### Key Attributes:

*   `emitted_material_name`: The material of the particles to emit (`spark_green`).
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines the velocity range for the emitted particles, creating a spread effect.
*   `count_min`, `count_max`: The number of particles to emit per burst.
*   `lifetime_min`, `lifetime_max`: Very short lifetimes, causing these sparks to disappear almost instantly.
*   `create_real_particles`: Set to `0`, indicating these are cosmetic particles.
*   `emit_cosmetic_particles`: Set to `1`, confirming these are cosmetic.
*   `is_emitting`: Set to `1`, meaning the emitter is active.

```xml
<ParticleEmitterComponent 
  emitted_material_name="spark_green"
  offset.x="0"
  offset.y="0"
  x_pos_offset_min="0"
  y_pos_offset_min="-1"
  x_pos_offset_max="0"
  y_pos_offset_max="1"
  x_vel_min="300"
  x_vel_max="50"
  y_vel_min="-50"
  y_vel_max="50"
  count_min="2"
  count_max="4"
  lifetime_min="0.0"
  lifetime_max="0.05"
  create_real_particles="0"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="0"
  emission_interval_max_frames="0"
  is_emitting="1" >
</ParticleEmitterComponent>
```

### Particle Emitter 2 (Lingering sparks)

This emitter creates a more sustained effect of green sparks that linger for a short duration.

#### Key Attributes:

*   `emitted_material_name`: The material of the particles to emit (`spark_green`).
*   `gravity.y`: Set to `0`, meaning these particles are not affected by gravity.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines a moderate velocity for these sparks.
*   `count_min`, `count_max`: The number of particles to emit per burst.
*   `lifetime_min`, `lifetime_max`: Longer lifetimes, allowing these sparks to persist.
*   `fade_based_on_lifetime`: Set to `1`, causing particles to fade out as their lifetime progresses.
*   `render_on_grid`: Set to `1`, indicating these particles should be rendered on the game grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These attributes suggest the particles are influenced by airflow, adding a subtle movement effect.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle bursts, creating a more continuous effect.
*   `create_real_particles`: Set to `0`, indicating these are cosmetic particles.
*   `emit_cosmetic_particles`: Set to `1`, confirming these are cosmetic.
*   `is_emitting`: Set to `1`, meaning the emitter is active.

```xml
<ParticleEmitterComponent 
  emitted_material_name="spark_green"
  offset.x="0"
  offset.y="0"
  gravity.y="0"
  x_pos_offset_min="0"
  y_pos_offset_min="0"
  x_pos_offset_max="0"
  y_pos_offset_max="0"
  x_vel_min="30"
  x_vel_max="50"
  y_vel_min="-10"
  y_vel_max="10"
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
  emission_interval_max_frames="7"
  is_emitting="1" >
</ParticleEmitterComponent>
```