---
title: Nuke Giga Projectile
category: entities
---

# Nuke Giga Projectile

This document details the `nuke_giga.xml` entity, representing a powerful, explosive projectile in Noita.

## Core Attributes

The `nuke_giga.xml` entity defines a projectile with significant damage, a large explosion radius, and various visual and audio effects.

### Entity Definition

```xml
<Entity 
  name="$projectile_default" tags="projectile_player,nuke_giga"
   >
```

*   **`name`**: Defaults to `$projectile_default`, indicating it inherits base projectile properties.
*   **`tags`**: `projectile_player` signifies it's a player-fired projectile. `nuke_giga` is a specific identifier for this projectile type.

### Base Projectile Properties

```xml
	<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="120" 
        air_friction="0.00001" 
		mass="0.2"
		>
    </VelocityComponent>
	</Base>
```

*   **`Base file`**: Inherits from `data/entities/base_projectile.xml`.
*   **`VelocityComponent`**:
    *   `gravity_y`: `120` - Applies moderate downward gravity.
    *   `air_friction`: `0.00001` - Negligible air resistance.
    *   `mass`: `0.2` - Low mass, contributing to its speed.

### Projectile Component - Key Settings

```xml
  <ProjectileComponent 
    _enabled="1" 
    lob_min="0.8"
    lob_max="1.0"
    speed_min="900"
    speed_max="900"
    direction_random_rad="0.01"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="0" 
    on_collision_die="1"
    lifetime="360"
    damage="10"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.04"
    hit_particle_force_multiplier="5.5 "
    camera_shake_when_shot="5.0" 
	muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml"
    shoot_light_flash_r="255"
    shoot_light_flash_g="210"
    shoot_light_flash_b="40"
    shoot_light_flash_radius="130"
	knockback_force="1.5"
	>
    <config_explosion
      never_cache="1" 
      camera_shake="60" 
      explosion_radius="400" 
      explosion_sprite="data/particles/explosion_032.xml"
	  load_this_entity="data/entities/particles/particle_explosion/main_large.xml,data/entities/misc/loose_chunks.xml,data/entities/misc/explosion_was_here.xml,data/entities/misc/radioactive_waste.xml"
      explosion_sprite_lifetime="0" 
      create_cell_probability="5" 
      hole_destroy_liquid="0" 
      hole_enabled="1" 
      ray_energy="9700000"
      damage="20"
      particle_effect="1" 
      damage_mortals="1"
	  physics_explosion_power.min="4.5"
      physics_explosion_power.max="9" 
      shake_vegetation="1" 
      sparks_count_max="1500" 
      sparks_count_min="1600" 
      sparks_enabled="1" 
      stains_enabled="1" 
      stains_radius="35"
      background_lightning_count="5" 
	  max_durability_to_destroy="14"
    audio_event_name="explosions/nuke"
	  >
    </config_explosion>
  </ProjectileComponent>
```

*   **`lob_min`/`lob_max`**: `0.8` to `1.0` - Controls the projectile's arc, making it relatively straight.
*   **`speed_min`/`speed_max`**: `900` - High, fixed speed.
*   **`on_death_explode`**: `1` - The projectile explodes upon death (e.g., collision or lifetime end).
*   **`on_lifetime_out_explode`**: `1` - Explodes when its lifetime expires.
*   **`on_collision_die`**: `1` - Dies and explodes upon hitting a surface.
*   **`lifetime`**: `360` - The projectile exists for 360 frames before expiring.
*   **`damage`**: `10` - Base damage of the projectile itself.
*   **`camera_shake_when_shot`**: `5.0` - Triggers a moderate camera shake when fired.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml` - Specifies the muzzle flash effect.
*   **`shoot_light_flash_*`**: Defines a bright, yellowish light flash upon firing.
*   **`knockback_force`**: `1.5` - Applies a knockback effect.
*   **`config_explosion`**:
    *   `camera_shake`: `60` - Significant camera shake upon explosion.
    *   `explosion_radius`: `400` - Very large explosion radius.
    *   `explosion_sprite`: `data/particles/explosion_032.xml` - The visual sprite for the explosion.
    *   `load_this_entity`: Lists entities spawned by the explosion, including `loose_chunks`, `explosion_was_here`, and `radioactive_waste`.
    *   `ray_energy`: `9700000` - Extremely high energy for destruction.
    *   `damage`: `20` - Damage dealt by the explosion.
    *   `physics_explosion_power.min`/`max`: `4.5` to `9` - Strong physics force applied by the explosion.
    *   `sparks_count_min`/`max`: `1600` to `1500` - Generates a very large number of sparks.
    *   `background_lightning_count`: `5` - Creates background lightning effects.
    *   `audio_event_name`: `explosions/nuke` - Triggers a specific nuke explosion sound.

### Sprite Component

```xml
  <SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/projectiles_gfx/nuke_giga.xml" 
    next_rect_animation="" 
    offset_x="0" 
    offset_y="0" 
    rect_animation="" 
     
     >
  </SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/nuke_giga.xml` - Specifies the visual asset for the projectile.

### Particle Emitters

This projectile utilizes multiple `ParticleEmitterComponent`s to create visual effects:

1.  **Spark Trail**:
    ```xml
      <ParticleEmitterComponent 
        emitted_material_name="spark"
        count_min="3"
        count_max="5"
        is_trail="1"
        trail_gap="0.5"
        lifetime_min="0.2"
        lifetime_max="0.6"
        create_real_particles="0"
        emit_cosmetic_particles="1"
        is_emitting="1" >
      </ParticleEmitterComponent>
    ```
    *   Emits `spark` particles as a trail.
    *   `is_trail="1"` and `trail_gap="0.5"` create a continuous visual effect.
    *   `emit_cosmetic_particles="1"` means these are purely visual.

2.  **Smoke Burst**:
    ```xml
      <ParticleEmitterComponent 
        emitted_material_name="smoke"
        count_min="1"
        count_max="5"
        lifetime_min="0.1"
        lifetime_max="0.3"
        create_real_particles="1"
        emit_cosmetic_particles="0"
        is_emitting="1" >
      </ParticleEmitterComponent>
    ```
    *   Emits `smoke` particles upon firing or impact.
    *   `create_real_particles="1"` suggests these might interact with the environment.

3.  **Radioactive Liquid Fading**:
    ```xml
      <ParticleEmitterComponent 
        emitted_material_name="radioactive_liquid_fading"
        count_min="1"
        count_max="5"
        lifetime_min="0.1"
        lifetime_max="0.3"
        create_real_particles="1"
        emit_cosmetic_particles="0"
        emission_interval_min_frames="0"
        emission_interval_max_frames="4"
        is_emitting="1" >
      </ParticleEmitterComponent>
    ```
    *   Emits particles of `radioactive_liquid_fading` material.
    *   The `emission_interval` suggests intermittent bursts.

### Audio Components

```xml
  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="projectiles/rocket">
  </AudioComponent>

  <AudioLoopComponent
      file="data/audio/Desktop/projectiles.bank"
      event_name="projectiles/rocket_passby"
      auto_play="1">
  </AudioLoopComponent>
```

*   **`AudioComponent`**: Plays a sound event associated with rockets when the projectile is active.
*   **`AudioLoopComponent`**: Plays a looping "passby" sound effect for the projectile.

### Variable Storage

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/nuke_giga.xml"
		>
	</VariableStorageComponent>
```

*   Stores the entity's own file path, likely for internal referencing.