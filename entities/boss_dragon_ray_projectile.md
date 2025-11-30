---
title: Boss Dragon Ray Projectile
category: entities
---

# Boss Dragon Ray Projectile

This document details the configuration of the `bossdragon_ray.xml` projectile entity in Noita, designed for AI-assisted modding.

## Core Entity

The projectile is based on the `base_projectile.xml` entity, inheriting fundamental projectile properties.

```xml
<Entity
  name="$projectile_default"
>
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			mass="0.05"
			>
    	</VelocityComponent>
	</Base>
  <!-- ... other components ... -->
</Entity>
```

## Projectile Component

This is the primary component defining the projectile's behavior and characteristics.

### Key Attributes:

*   **`speed_min` / `speed_max`**: Defines the projectile's speed. Set to `1000` for a consistent high speed.
*   **`lifetime`**: Duration the projectile exists before expiring. Set to `20` frames.
*   **`lifetime_randomness`**: Adds variability to the projectile's lifetime. Set to `7` frames.
*   **`damage`**: Base damage dealt by the projectile. Set to a low `0.1`.
*   **`knockback_force`**: The force applied to entities upon impact. Set to `0.5`.
*   **`camera_shake_when_shot`**: Intensity of camera shake when this projectile is fired. Set to `2.0`.
*   **`shoot_light_flash_radius`**: Radius of the light flash effect when shot. Set to `100`.
*   **`on_death_explode`**: If `1`, the projectile explodes upon death.
*   **`on_lifetime_out_explode`**: If `1`, the projectile explodes when its lifetime expires.
*   **`on_collision_die`**: If `1`, the projectile is destroyed upon collision.
*   **`explosion_dont_damage_shooter`**: If `1`, the explosion does not damage the entity that shot it.

### `config_explosion` Sub-element:

Defines the properties of the explosion triggered by the projectile.

*   **`ray_energy`**: A significant value (`50000`) indicating high energy for the explosion.
*   **`explosion_radius`**: The area of effect for the explosion. Set to `10`.
*   **`camera_shake`**: Intensity of camera shake during the explosion. Set to `5`.
*   **`damage`**: Damage dealt by the explosion itself. Set to `0.05`.
*   **`hole_enabled`**: If `1`, creates a hole in the environment.
*   **`physics_throw_enabled`**: If `1`, the explosion can throw physics objects.
*   **`damage_mortals`**: If `1`, the explosion damages living entities.

```xml
  <ProjectileComponent
    _enabled="1"
    lob_min="0.8"
    lob_max="1.0"
    speed_min="1000"
    speed_max="1000"
    friction="1.2"
    direction_random_rad="0.1"
    die_on_low_velocity="1"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    on_collision_die="1"
    lifetime="20"
    damage="0.1"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.0025"
    hit_particle_force_multiplier="0.25 "
    camera_shake_when_shot="2.0"
    shoot_light_flash_radius="100"
    knockback_force="0.5"
    >
    <config_explosion
      never_cache="1"
      camera_shake="5"
      explosion_radius="10"
      explosion_sprite="data/particles/explosion_008.xml"
      explosion_sprite_lifetime="0"
      create_cell_probability="0"
      hole_destroy_liquid="0"
      hole_enabled="1"
      ray_energy="50000"
      damage="0.05"
      hole_image="data/temp/explosion_hole.png"
      particle_effect="0 "
      damage_mortals="1"
	    physics_explosion_power.min="0.2"
      physics_explosion_power.max="0.4"
      physics_throw_enabled="1"
      shake_vegetation="1"
      sparks_count_max="1"
      sparks_count_min="1"
      sparks_enabled="1"
      light_enabled="1"
      stains_enabled="1"
      stains_radius="1"
      audio_enabled="0" >
    </config_explosion>
  </ProjectileComponent>
```

## Sprite Component

Defines the visual representation of the projectile.

*   **`image_file`**: Specifies the sprite to be used. Here, it's `data/projectiles_gfx/fireball_small.xml`.
*   **`offset_x` / `offset_y`**: Adjusts the sprite's position relative to the projectile's origin.

```xml
  <SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/fireball_small.xml"
    next_rect_animation=""
    offset_x="2"
    offset_y="2"
    rect_animation=""
     >
  </SpriteComponent>
```

## Particle Emitter Component

Manages the emission of particles, likely for a trail effect.

*   **`emitted_material_name`**: The material of the particles to emit, set to `"spark"`.
*   **`is_trail`**: If `1`, the particles form a trail.
*   **`trail_gap`**: The spacing between trail particles. Set to `2`.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the frequency of particle emission.
*   **`emit_cosmetic_particles`**: If `1`, emits particles that are purely visual.

```xml
  <ParticleEmitterComponent
    emitted_material_name="spark"
    offset.x="0"
    offset.y="0"
    x_pos_offset_min="-1"
    y_pos_offset_min="-1"
    x_pos_offset_max="1"
    y_pos_offset_max="1"
    x_vel_min="-10"
    x_vel_max="10"
    y_vel_min="0"
    y_vel_max="0"
    count_min="1"
    count_max="1"
    lifetime_min="0.1"
    lifetime_max="0.3"
  	fade_based_on_lifetime="1"
  	is_trail="1"
  	trail_gap="2"
    create_real_particles="0"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="4"
    emission_interval_max_frames="5"
    is_emitting="1" >
  </ParticleEmitterComponent>
```

## Audio Component

Handles the sound effects associated with the projectile.

*   **`file`**: The audio bank containing the sound events.
*   **`event_root`**: The specific sound event to trigger.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="projectiles/flamethrower">
	</AudioComponent>
```

## Variable Storage Component

Stores custom variables for the entity.

*   **`name`**: The name of the variable.
*   **`value_string`**: The string value of the variable. Here, it stores the projectile's own file path.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/bossdragon_ray.xml"
		>
	</VariableStorageComponent>
```