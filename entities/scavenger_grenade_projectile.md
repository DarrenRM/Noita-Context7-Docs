---
title: Scavenger Grenade Projectile
category: entities
---

# Scavenger Grenade Projectile

This document details the configuration for the Scavenger Grenade projectile in Noita, focusing on its key attributes for AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior of the grenade.

### Key Attributes:

*   **`lob_min`, `lob_max`**: Controls the minimum and maximum lob angle (0.9 to 1.0 suggests a very slight lob).
*   **`speed_min`, `speed_max`**: Sets the initial velocity range of the projectile (150 to 180 units/second).
*   **`friction`**: How much the projectile slows down in the air (0.6).
*   **`direction_random_rad`**: Random deviation in projectile direction (0.05 radians).
*   **`on_death_explode`**: If the projectile explodes upon death (1 = true).
*   **`on_lifetime_out_explode`**: If the projectile explodes when its lifetime expires (1 = true).
*   **`on_collision_die`**: If the projectile dies upon collision (1 = true).
*   **`lifetime`**: The maximum duration of the projectile in frames (500 frames).
*   **`damage`**: The base damage dealt by the projectile (1.3).
*   **`bounces_left`**: The number of bounces the projectile can perform before dying (4).
*   **`knockback_force`**: The force applied to entities upon impact (1.7).

## Explosion Configuration

The `config_explosion` section within `ProjectileComponent` defines the effects when the projectile explodes.

### Key Attributes:

*   **`camera_shake`**: Intensity of camera shake upon explosion (10).
*   **`explosion_radius`**: The radius of the explosion effect (10).
*   **`explosion_sprite`**: Path to the sprite used for the explosion visual (e.g., `data/particles/explosion_016.xml`).
*   **`load_this_entity`**: The entity to spawn upon explosion (e.g., `data/entities/particles/particle_explosion/main_gunpowder_tiny.xml`).
*   **`ray_energy`**: Energy value for raycasting effects from the explosion (25000).
*   **`damage`**: Damage dealt by the explosion itself (0, likely meaning damage is handled by other components or the projectile itself).
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: Minimum and maximum force applied to physics objects by the explosion.
*   **`sparks_enabled`**: Whether sparks are generated (1 = true).
*   **`stains_enabled`**: Whether impact stains are generated (1 = true).
*   **`stains_radius`**: The radius of the impact stains (12).
*   **`audio_event_name`**: The name of the audio event to play for the explosion (e.g., `explosions/grenade_small`).

## Visual Representation

The `SpriteComponent` defines the visual appearance of the projectile.

### Key Attributes:

*   **`image_file`**: Path to the sprite file for the projectile (e.g., `data/projectiles_gfx/grenade_scavenger_small.xml`).

## Particle Effects

The `ParticleEmitterComponent` handles the emission of particles, such as smoke.

### Key Attributes:

*   **`emitted_material_name`**: The material of the particles to emit (e.g., `smoke`).
*   **`count_min`, `count_max`**: The number of particles emitted per emission cycle.
*   **`lifetime_min`, `lifetime_max`**: The duration of emitted particles.
*   **`is_emitting`**: Whether the particle emitter is active (1 = true).

## Lighting

The `LightComponent` adds a light source to the projectile.

### Key Attributes:

*   **`radius`**: The radius of the light emitted (40).

## Audio

The `AudioComponent` specifies the sound effects associated with the projectile.

### Key Attributes:

*   **`file`**: The audio bank file containing the sound events.
*   **`event_root`**: The root event name for projectile sounds.

## Variable Storage

The `VariableStorageComponent` is used to store custom variables.

### Key Attributes:

*   **`name`**: The name of the variable (`projectile_file`).
*   **`value_string`**: The string value of the variable, pointing to the projectile's own XML file.

```xml
<Entity name="$projectile_default">

	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			air_friction="0.0"
			mass="0.06"
			>
		</VelocityComponent>
	</Base>

  <ProjectileComponent 
    lob_min="0.9"
    lob_max="1.0"
    speed_min="150"
    speed_max="180"
    friction="0.6"
    direction_random_rad="0.05"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="0" 
    on_collision_die="1"
    lifetime="500"
    damage="1.3"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.04"
    hit_particle_force_multiplier="5.5 "
    bounces_left="4"
    camera_shake_when_shot="5.0"
    shoot_light_flash_radius="80"
	muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_launcher.xml"
	knockback_force="1.7"
	>
    <config_explosion
      never_cache="0" 
      camera_shake="10" 
      explosion_radius="10"
      explosion_sprite="data/particles/explosion_016.xml" 
      load_this_entity="data/entities/particles/particle_explosion/main_gunpowder_tiny.xml"
      explosion_sprite_lifetime="0" 
      create_cell_probability="0" 
      hole_destroy_liquid="0" 
      hole_enabled="1" 
      ray_energy="25000"
      damage="0"
      particle_effect="0"
      damage_mortals="1"
	  physics_explosion_power.min="0.15"
      physics_explosion_power.max="0.35" 
      shake_vegetation="1" 
      sparks_count_min="4" 
      sparks_count_max="10" 
      sparks_enabled="1" 
      stains_enabled="1"
      stains_radius="12"
      audio_event_name="explosions/grenade_small" >
    </config_explosion>
  </ProjectileComponent>
  
  <SpriteComponent 
    alpha="1" 
    image_file="data/projectiles_gfx/grenade_scavenger_small.xml" 
    next_rect_animation="" 
    offset_x="0" 
    offset_y="0" 
    rect_animation="" 
    >
  </SpriteComponent>

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
    count_max="1"
    lifetime_min="0.1"
    lifetime_max="0.3"
    create_real_particles="1"
    emit_cosmetic_particles="0"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    is_emitting="1" >
  </ParticleEmitterComponent>

  <LightComponent 
    radius="40" >
  </LightComponent>

  <AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="projectiles/bullet_launcher">
  </AudioComponent>
  
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/grenade_scavenger.xml"
		>
	</VariableStorageComponent>
  
</Entity>
```