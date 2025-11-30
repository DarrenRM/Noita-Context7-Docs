---
title: Large Magic Muzzle Flash Particle
category: entities
---

# Large Magic Muzzle Flash Particle

This entity defines a large, magical muzzle flash effect for projectiles in Noita. It utilizes multiple `ParticleEmitterComponent`s to generate distinct visual elements, contributing to a dynamic and visually appealing flash.

## SpriteComponent

This component handles the visual representation of the muzzle flash itself.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet used for the animation. The `$[1-5]` indicates a sequence of 5 frames.
*   `rect_animation`: The name of the animation sequence defined within the sprite sheet.
*   `next_rect_animation`: The name of the animation to transition to after the current one finishes.
*   `emissive`: Set to `1` to make the sprite emit light.
*   `additive`: Set to `1` for additive blending, common for bright light effects.
*   `kill_entity_after_finished`: Set to `1` to automatically remove the entity once the sprite animation is complete.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's origin.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/particles/muzzle_flashes/muzzle_magic_large_0$[1-5].png" 
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

## ParticleEmitterComponent (Spark Effect)

This emitter generates small, fast-moving "spark" particles.

### Key Attributes:

*   `emitted_material_name`: The material name for the particles being emitted (`spark_blue`).
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines the area around the emitter where particles can spawn.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range for the emitted particles.
*   `count_min`, `count_max`: The number of particles to emit per burst.
*   `lifetime_min`, `lifetime_max`: The duration each particle will exist. Set to `0.0` for very short-lived particles.
*   `create_real_particles`: Set to `0` to emit cosmetic particles that don't interact with the physics world.
*   `emit_cosmetic_particles`: Set to `1` to ensure these are cosmetic.
*   `is_emitting`: Set to `1` to enable emission.

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
  count_max="8"
  lifetime_min="0.0"
  lifetime_max="0.05"
  create_real_particles="0"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="0"
  emission_interval_max_frames="0"
  is_emitting="1" >
</ParticleEmitterComponent>
```

## ParticleEmitterComponent (Plasma Effect)

This emitter generates larger, fading "plasma" particles with a longer lifespan and some environmental interaction.

### Key Attributes:

*   `emitted_material_name`: The material name for the particles being emitted (`plasma_fading`).
*   `gravity.y`: Controls the gravitational pull on the particles. Set to `0` for no gravity.
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines the spawn area. Here, it's a very small area around the origin.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range.
*   `count_min`, `count_max`: The number of particles to emit per burst.
*   `lifetime_min`, `lifetime_max`: The duration each particle will exist.
*   `fade_based_on_lifetime`: Set to `1` to make particles fade out as their lifetime approaches zero.
*   `render_on_grid`: Set to `1` to allow particles to be rendered on the game grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters that influence how particles react to airflow in the game world.
*   `create_real_particles`: Set to `0` for cosmetic particles.
*   `emit_cosmetic_particles`: Set to `1` to ensure these are cosmetic.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle bursts.
*   `is_emitting`: Set to `1` to enable emission.

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
  x_vel_min="30"
  x_vel_max="70"
  y_vel_min="-2"
  y_vel_max="2"
  count_min="1"
  count_max="3"
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