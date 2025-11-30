---
title: Rocket Tank Projectile
category: entities
---

# Rocket Tank Projectile

This document details the configuration of the `rocket_tank.xml` entity, which defines the behavior and appearance of the Rocket Tank projectile in Noita.

## Core Components

### Entity Definition

The root `Entity` tag defines the projectile and its general properties.

```xml
<Entity 
  name="$projectile_default" 
  tags="teleportable_NOT,projectile"
>
  <!-- ... components ... -->
</Entity>
```

*   **`name`**: Set to `$projectile_default`, indicating it uses default projectile naming conventions.
*   **`tags`**:
    *   `teleportable_NOT`: This projectile cannot be teleported.
    *   `projectile`: Identifies this entity as a projectile.

### Velocity Component

Controls the physical movement and gravity of the projectile.

```xml
<VelocityComponent 
  gravity_y="0"
  mass="0.1"
>
</VelocityComponent>
```

*   **`gravity_y`**: Set to `0`, meaning the projectile is not affected by gravity in the Y-axis.
*   **`mass`**: A low mass of `0.1`, contributing to its speed and responsiveness.

### Homing Component

Enables the projectile to track targets.

```xml
<HomingComponent
  target_tag="prey"
  homing_targeting_coeff="15"
  detect_distance="300"
  homing_velocity_multiplier="1.0"
>
</HomingComponent>
```

*   **`target_tag`**: The projectile will attempt to home in on entities with the tag `prey`.
*   **`homing_targeting_coeff`**: A high coefficient (`15`) indicates strong homing behavior.
*   **`detect_distance`**: The projectile can detect targets within `300` units.
*   **`homing_velocity_multiplier`**: The projectile's velocity is multiplied by `1.0` when homing.

### Projectile Component

This is the primary component defining the projectile's behavior, including its damage, lifespan, explosion properties, and visual effects.

```xml
<ProjectileComponent 
  _enabled="1" 
  lob_min="0.8"
  lob_max="1.0"
  speed_min="80"
  speed_max="80"
  friction="-1.0"
  direction_random_rad="0.05"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0" 
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="0" 
  on_collision_die="1"
  lifetime="100"
  damage="1"
  velocity_sets_scale="1"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0.04"
  hit_particle_force_multiplier="5.5"
  camera_shake_when_shot="5.0" 
  bounces_left="1"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml"
  shoot_light_flash_r="255"
  shoot_light_flash_g="210"
  shoot_light_flash_b="40"
  shoot_light_flash_radius="90"
  knockback_force="2.0"
>
  <config_explosion
    never_cache="1" 
    camera_shake="20" 
    explosion_radius="10" 
    explosion_sprite="data/particles/explosion_032.xml" 
    explosion_sprite_lifetime="0" 
    create_cell_probability="5" 
    hole_destroy_liquid="0"
    load_this_entity="data/entities/particles/particle_explosion/main_gunpowder_tiny.xml"
    explosion_sprite_emissive="1"
    explosion_sprite_additive="1"
    hole_enabled="1" 
    ray_energy="100000"
    damage="0.5"
    particle_effect="1" 
    damage_mortals="1"
    physics_explosion_power.min="0.5" 
    physics_explosion_power.max="0.7"
    physics_throw_enabled="1"
    shake_vegetation="1" 
    sparks_count_max="20" 
    sparks_count_min="7" 
    sparks_enabled="1" 
    stains_enabled="1" 
    stains_radius="15"
    audio_event_name="explosions/tnt" >
  </config_explosion>
</ProjectileComponent>
```

*   **`lob_min`/`lob_max`**: Controls the initial upward angle of the projectile.
*   **`speed_min`/`speed_max`**: Sets the projectile's speed to a constant `80`.
*   **`friction`**: `-1.0` suggests no friction or unusual behavior.
*   **`direction_random_rad`**: Introduces a small amount of randomness (`0.05` radians) to the projectile's initial direction.
*   **`on_death_explode`**: Set to `1`, the projectile explodes when it dies.
*   **`on_lifetime_out_explode`**: Set to `1`, the projectile explodes when its lifetime expires.
*   **`on_collision_die`**: Set to `1`, the projectile dies upon collision.
*   **`lifetime`**: The projectile exists for `100` frames.
*   **`damage`**: The projectile deals `1` damage on impact (before explosion).
*   **`lifetime_randomness`**: Adds up to `7` frames of randomness to the projectile's lifetime.
*   **`camera_shake_when_shot`**: Causes `5.0` units of camera shake when the projectile is fired.
*   **`bounces_left`**: The projectile can bounce `1` time.
*   **`muzzle_flash_file`**: Specifies the muzzle flash particle effect.
*   **`shoot_light_flash_*`**: Defines the color and radius of the light flash when the projectile is shot.
*   **`knockback_force`**: Applies `2.0` force for knockback on impact.
*   **`config_explosion`**:
    *   **`camera_shake`**: `20` units of camera shake on explosion.
    *   **`explosion_radius`**: The explosion affects an area of `10` units.
    *   **`explosion_sprite`**: The visual sprite for the explosion.
    *   **`load_this_entity`**: Loads a specific particle effect for the explosion.
    *   **`ray_energy`**: High `100000` ray energy, indicating significant destructive potential.
    *   **`damage`**: The explosion deals `0.5` damage.
    *   **`damage_mortals`**: The explosion damages mortals.
    *   **`physics_explosion_power`**: Controls the physics force of the explosion.
    *   **`sparks_enabled`**: Sparks are generated by the explosion.
    *   **`stains_enabled`**: Creates stains on surfaces from the explosion.
    *   **`audio_event_name`**: Triggers the `explosions/tnt` sound event.

### Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/projectiles_gfx/rocket.xml" 
  offset_x="0" 
  offset_y="0" 
>
</SpriteComponent>
```

*   **`image_file`**: Specifies the sprite image used for the projectile (`data/projectiles_gfx/rocket.xml`).

### Particle Emitter Components

These components generate visual effects like smoke and fire trails.

#### Smoke Emitter

```xml
<ParticleEmitterComponent 
  emitted_material_name="smoke"
  offset.x="0"
  offset.y="0"
  x_pos_offset_min="-1"
  y_pos_offset_min="-1"
  x_pos_offset_max="1"
  y_pos_offset_max="1"
  x_vel_min="-10"
  x_vel_max="10"
  y_vel_min="-10"
  y_vel_max="10"
  count_min="5"
  count_max="5"
  lifetime_min="0.1"
  lifetime_max="0.3"
  create_real_particles="1"
  is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: Emits particles of type `smoke`.
*   **`count_min`/`count_max`**: Emits `5` smoke particles per emission.
*   **`lifetime_min`/`lifetime_max`**: Smoke particles last between `0.1` and `0.3` seconds.

#### Fire Emitter

```xml
<ParticleEmitterComponent 
  emitted_material_name="fire"
  offset.x="0"
  offset.y="0"
  x_pos_offset_min="-1"
  y_pos_offset_min="-1"
  x_pos_offset_max="1"
  y_pos_offset_max="1"
  x_vel_min="-2"
  x_vel_max="2"
  y_vel_min="-5"
  y_vel_max="0"
  count_min="1"
  count_max="1"
  lifetime_min="0.1"
  lifetime_max="0.4"
  create_real_particles="1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="3"
  is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: Emits particles of type `fire`.
*   **`count_min`/`count_max`**: Emits `1` fire particle per emission.
*   **`lifetime_min`/`lifetime_max`**: Fire particles last between `0.1` and `0.4` seconds.
*   **`emission_interval_min_frames`/`emission_interval_max_frames`**: Fire particles are emitted every `1` to `3` frames.

#### Sprite Particle Emitter (Smoke Trail)

This component uses a specific sprite for a more detailed smoke trail effect.

```xml
<SpriteParticleEmitterComponent
  sprite_file="data/particles/smoke_orange.xml"
  delay="0"
  lifetime="0"
  emissive="0"
  sprite_random_rotation="1"
  color.r="1" color.g="1" color.b="1" color.a="1"
  velocity.x="0" velocity.y="0"
  gravity.x="0" gravity.y="0"
  velocity_slowdown="0.5"
  rotation="0"
  angular_velocity="0"
  use_velocity_as_rotation="0"
  scale.x="1" scale.y="1"
  scale_velocity.x="-0.1" scale_velocity.y="-0.1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  count_min="1" count_max="1"
  randomize_rotation.min="-3.1415"
  randomize_rotation.max="3.1415"
  randomize_angular_velocity.min="-1"
  randomize_angular_velocity.max="1"
  randomize_position.min_x="-2"
  randomize_position.max_x="2"
  randomize_position.min_y="-2"
  randomize_position.max_y="2"
  randomize_velocity.min_y="0"
  randomize_velocity.max_y="2"
  randomize_velocity.min_x="-2"
  randomize_velocity.max_x="2"
  render_back="1"
>
</SpriteParticleEmitterComponent>
```

*   **`sprite_file`**: Uses `data/particles/smoke_orange.xml` for the sprite.
*   **`scale_velocity.x`/`scale_velocity.y`**: Particles shrink over time (`-0.1`).
*   **`randomize_rotation`**: Particles have random initial rotations.
*   **`randomize_angular_velocity`**: Particles have random angular velocities.
*   **`randomize_position`**: Particles are emitted with slight positional randomness.

### Audio Component

Handles the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="projectiles/rocket">
</AudioComponent>
```

*   **`file`**: Specifies the audio bank file.
*   **`event_root`**: Sets the root event for projectile sounds.

### Audio Loop Component

Plays a continuous sound effect while the projectile is active.

```xml
<AudioLoopComponent
    file="data/audio/Desktop/projectiles.bank"
    event_name="projectiles/rocket_passby"
    auto_play="1">
</AudioLoopComponent>
```

*   **`event_name`**: Plays the `projectiles/rocket_passby` sound event.
*   **`auto_play`**: The sound starts automatically when the projectile is created.

### Variable Storage Component

Stores a reference to the projectile's own entity file.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/rocket_tank.xml"
>
</VariableStorageComponent>
```

*   **`name`**: `projectile_file`.
*   **`value_string`**: Stores the path to this entity's XML file.