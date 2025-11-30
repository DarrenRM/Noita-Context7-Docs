---
title: Tiny Rocket Projectile
category: entities
---

# Tiny Rocket Projectile

This document details the configuration of the "Tiny Rocket" projectile entity in Noita, focusing on its behavior, visual representation, and particle effects.

## Core Entity Configuration

The base entity is defined as a projectile with the name `$projectile_default`, indicating it inherits default projectile properties. It is tagged as `teleportable_NOT` (cannot be teleported) and `projectile`.

```xml
<Entity 
  name="$projectile_default" 
  tags="teleportable_NOT,projectile"
>
```

## Velocity Component

This projectile has no gravity applied to it.

```xml
	<VelocityComponent 
		gravity_y="0"
	>
	</VelocityComponent>
```

## Homing Component

The projectile exhibits homing behavior, targeting entities with the `prey` tag.

*   **`homing_targeting_coeff`**: Controls the strength of the homing effect (15).
*   **`detect_distance`**: The range at which the projectile can detect targets (200 units).
*   **`homing_velocity_multiplier`**: A multiplier for the homing velocity (1.0).

```xml
	<HomingComponent
		target_tag="prey"
		homing_targeting_coeff="15"
		detect_distance="200"
		homing_velocity_multiplier="1.0"
	>
	</HomingComponent>
```

## Projectile Component

This is the primary component defining the projectile's behavior.

*   **`lob_min`/`lob_max`**: Defines the minimum and maximum lob angle (0.8 to 1.0).
*   **`speed_min`/`speed_max`**: The projectile travels at a constant speed of 80.
*   **`friction`**: Set to -1.0, indicating no friction.
*   **`direction_random_rad`**: Introduces a small amount of randomness to the projectile's initial direction (0.05 radians).
*   **`on_death_explode`**: The projectile explodes upon death (1).
*   **`on_lifetime_out_explode`**: The projectile also explodes when its lifetime expires (1).
*   **`on_collision_die`**: The projectile dies upon collision (1).
*   **`lifetime`**: The projectile exists for 150 frames, with `lifetime_randomness` of 7 frames.
*   **`damage`**: Deals 0.8 damage.
*   **`bounces_left`**: The projectile can bounce once (1).
*   **`camera_shake_when_shot`**: Triggers camera shake when fired (5.0).

### Explosion Configuration (`config_explosion`)

When the projectile explodes, it has the following properties:

*   **`camera_shake`**: Significant camera shake (20).
*   **`explosion_radius`**: The radius of the explosion (10 units).
*   **`explosion_sprite`**: Uses `data/particles/explosion_016.xml` for the explosion visual.
*   **`create_cell_probability`**: A 5% chance to create cells upon explosion.
*   **`hole_enabled`**: Creates holes in terrain (1).
*   **`ray_energy`**: High ray energy (80000).
*   **`damage`**: Deals 1 damage in the explosion.
*   **`physics_explosion_power`**: Applies physics force with a minimum of 0.30 and a maximum of 0.45.
*   **`sparks_enabled`**: Generates sparks (1) with a count between 7 and 20.
*   **`stains_enabled`**: Leaves stains (1) with a radius of 15.

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
    lifetime="150"
    damage="0.8"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.04"
    hit_particle_force_multiplier="5.5 "
    camera_shake_when_shot="5.0" 
    bounces_left="1"
    shoot_light_flash_radius="80" >
    <config_explosion
      never_cache="1" 
      camera_shake="20" 
      explosion_radius="10" 
      explosion_sprite="data/particles/explosion_016.xml" 
      explosion_sprite_lifetime="0" 
      create_cell_probability="5" 
      hole_destroy_liquid="0"
	  explosion_sprite_emissive="1"
	  explosion_sprite_additive="1"
      hole_enabled="1" 
      ray_energy="80000"
      damage="1"
      particle_effect="1" 
      damage_mortals="1"
	  physics_explosion_power.min="0.30" 
      physics_explosion_power.max="0.45" 
      physics_throw_enabled="1"
      shake_vegetation="1" 
      sparks_count_max="20" 
      sparks_count_min="7" 
      sparks_enabled="1" 
      stains_enabled="1" 
      stains_radius="15" >
    </config_explosion>
  </ProjectileComponent>
```

## Sprite Component

The visual representation of the projectile is defined here.

*   **`image_file`**: Points to `data/projectiles_gfx/rocket_tiny.xml` for the sprite.
*   **`emissive`**: Set to 1, meaning the sprite emits light.

```xml
  <SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/projectiles_gfx/rocket_tiny.xml" 
    next_rect_animation="" 
    offset_x="0" 
    offset_y="0" 
    rect_animation="" 
    emissive="1" >
  </SpriteComponent>
```

## Particle Emitter Components

Two particle emitters are used to create visual effects.

### Smoke Emitter

*   **`emitted_material_name`**: `smoke`.
*   **`count_min`/`count_max`**: Emits 1 to 2 particles per emission.
*   **`lifetime_min`/`lifetime_max`**: Particles last between 0.1 and 0.3 seconds.
*   **`create_real_particles`**: Set to 1, meaning these are actual game particles.
*   **`emission_interval_min_frames`/`emission_interval_max_frames`**: Emits every 1 frame.

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
    count_min="1"
    count_max="2"
    lifetime_min="0.1"
    lifetime_max="0.3"
    create_real_particles="1"
    emit_cosmetic_particles="0"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    is_emitting="1" >
  </ParticleEmitterComponent>
```

### Spark Emitter

*   **`emitted_material_name`**: `spark`.
*   **`count_min`/`count_max`**: Emits 1 spark per emission.
*   **`lifetime_min`/`lifetime_max`**: Particles last between 0.1 and 0.4 seconds.
*   **`is_trail`**: This emitter creates a trail effect.
*   **`emit_cosmetic_particles`**: Set to 1, meaning these are cosmetic particles.
*   **`emission_interval_min_frames`/`emission_interval_max_frames`**: Emits every 1 to 2 frames.

```xml
  <ParticleEmitterComponent 
    emitted_material_name="spark"
    count_min="1"
    count_max="1"
	x_pos_offset_min="-2"
    y_pos_offset_min="-1"
    x_pos_offset_max="2"
    y_pos_offset_max="1"
    offset.x="0"
    offset.y="0"
	gravity.y="0"
    count_min="1"
    count_max="1"
    lifetime_min="0.1"
    lifetime_max="0.4"
	is_trail="1"
	trail_gap="0.5"
	fade_based_on_lifetime="0"
    emit_real_particles="0"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="2"
    is_emitting="1" >
  </ParticleEmitterComponent>
```

## Audio Component

The projectile plays sounds from the `projectiles.bank` audio file, with the event root set to `projectiles/rocket`.

```xml
  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="projectiles/rocket">
  </AudioComponent>
```

## Variable Storage Component

Stores the projectile's own file path for potential referencing.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/rocket_tiny_particles.xml"
	>
	</VariableStorageComponent>
```