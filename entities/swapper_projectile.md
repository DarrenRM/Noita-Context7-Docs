---
title: Swapper Projectile
category: entities
---

---

# Swapper Projectile

This document details the configuration of the Swapper projectile entity in Noita, useful for AI-assisted modding.

## Entity Definition

The core entity definition for the Swapper projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  <!-- ... components ... -->
</Entity>
```

-   `name`: `$projectile_default` - Standard name for default projectiles.
-   `tags`: `projectile_player` - Identifies this as a projectile fired by the player.

## Base Projectile Configuration

Inherits base properties from `base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml" >
  <VelocityComponent
    gravity_y="200"
    air_friction="1.7"
    mass="0.04"
  ></VelocityComponent>
</Base>
```

-   `gravity_y`: `200` - Controls the downward acceleration due to gravity.
-   `air_friction`: `1.7` - Resistance to movement in the air.
-   `mass`: `0.04` - The projectile's mass, affecting its momentum.

## Hit Effect Component

Defines the special effect triggered upon hitting a target.

```xml
<HitEffectComponent 
    effect_hit="SWAPPER"
></HitEffectComponent >
```

-   `effect_hit`: `SWAPPER` - This is the key identifier for the swapper effect.

## Projectile Component

Manages the projectile's behavior, trajectory, and effects.

```xml
<ProjectileComponent 
  _enabled="1" 
  lob_min="0.5"
  lob_max="0.7"
  speed_min="750"
  speed_max="850"
  friction="1"
  direction_random_rad="0.00"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0" 
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1"
  on_collision_die="1"
  on_collision_remove_projectile="0"
  lifetime="40"
  damage="0"
  velocity_sets_scale="1"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0.005"
  hit_particle_force_multiplier="0.1"
  create_shell_casing="0"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_small.xml"
  shoot_light_flash_radius="120" 
  shoot_light_flash_r="140"
  shoot_light_flash_g="210"
  shoot_light_flash_b="255"
>
  <config_explosion
    never_cache="1" 
    damage="0.0"
    camera_shake="0.5" 
    explosion_radius="2" 
    explosion_sprite="data/particles/explosion_016_plasma.xml" 
    explosion_sprite_lifetime="0" 
    create_cell_probability="0" 
    hole_destroy_liquid="0"
    explosion_sprite_additive="1"
    hole_enabled="1" 
    ray_energy="40000"
    particle_effect="0" 
    damage_mortals="1"
    physics_explosion_power.min="0" 
    physics_explosion_power.max="0" 
    physics_throw_enabled="0" 
    shake_vegetation="1" 
    sparks_count_max="20" 
    sparks_count_min="7" 
    sparks_enabled="0"  
    material_sparks_enabled="1"
    material_sparks_count_max="2"
    material_sparks_count_min="0" 
    light_enabled="0" 
    stains_enabled="1"
    stains_radius="3" >
  </config_explosion>
</ProjectileComponent>
```

### Key Attributes:

-   `lob_min`/`lob_max`: `0.5`/`0.7` - Controls the arc of the projectile.
-   `speed_min`/`speed_max`: `750`/`850` - Initial velocity range.
-   `lifetime`: `40` - How long the projectile exists before expiring.
-   `damage`: `0` - This projectile itself does no direct damage.
-   `on_death_explode`: `1` - The projectile explodes when it dies (e.g., on collision or lifetime out).
-   `explosion_dont_damage_shooter`: `1` - The explosion will not harm the player who fired it.
-   `on_collision_die`: `1` - The projectile dies upon collision.
-   `lifetime_randomness`: `7` - Adds variation to the projectile's lifespan.
-   `shoot_light_flash_radius`/`r`/`g`/`b`: Defines the light effect when the projectile is fired.

### `config_explosion`:

-   `damage`: `0.0` - The explosion itself does no damage.
-   `camera_shake`: `0.5` - Amount of camera shake on explosion.
-   `explosion_radius`: `2` - The radius of the explosion effect.
-   `hole_enabled`: `1` - Creates a hole in terrain.
-   `ray_energy`: `40000` - Energy for terrain destruction.
-   `damage_mortals`: `1` - While the projectile damage is 0, the explosion can damage mortals.
-   `shake_vegetation`: `1` - Causes vegetation to shake.
-   `stains_enabled`: `1` - Leaves stains on surfaces.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/projectiles_gfx/orb_blue.xml" 
  offset_x="5" 
  offset_y="5" 
  rect_animation="fireball" 
  emissive="1"
  additive="1"
  update_transform_rotation="0"
>
</SpriteComponent>
```

-   `image_file`: `data/projectiles_gfx/orb_blue.xml` - The sprite asset used.
-   `rect_animation`: `fireball` - Specifies the animation to use.
-   `emissive`/`additive`: `1` - Affects how the sprite is rendered, often for glowing effects.

## Light Component

Adds a light source to the projectile.

```xml
<LightComponent 
  _enabled="1" 
  radius="150" 
  r="40"
  g="18"
  b="220">
</LightComponent>
```

-   `radius`: `150` - The range of the light.
-   `r`/`g`/`b`: `40`/`18`/`220` - The color of the light (blueish).

## Audio Component

Handles sound effects associated with the projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="player_projectiles/swapper"
></AudioComponent>
```

-   `file`: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sounds.
-   `event_root`: `player_projectiles/swapper` - The specific sound event for this projectile.

## Particle Emitter Components

Two emitters are used to create visual effects.

### Emitter 1 (Trail)

```xml
<ParticleEmitterComponent 
  emitted_material_name="spark_blue"
  offset.x="0"
  gravity.y="-10.0"
  offset.y="0"
  count_min="70"
  count_max="140"
  x_pos_offset_min="-2"
  y_pos_offset_min="-1"
  x_pos_offset_max="2"
  y_pos_offset_max="1"
  x_vel_min="-10"
  x_vel_max="10"
  y_vel_min="0"
  y_vel_max="0"
  is_trail="1"
  trail_gap="1.5"
  lifetime_min="0.4"
  lifetime_max="0.6"
  airflow_force="0.1"
  airflow_time="0.101"
  airflow_scale="2.01"
  emit_real_particles="0"
  fade_based_on_lifetime="1"
  render_on_grid="1"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  is_emitting="1" 
></ParticleEmitterComponent>
```

-   `emitted_material_name`: `spark_blue` - The type of particle emitted.
-   `is_trail`: `1` - Indicates this emitter creates a trail effect.
-   `lifetime_min`/`lifetime_max`: `0.4`/`0.6` - Short lifespan for trail particles.

### Emitter 2 (Main Effect)

```xml
<ParticleEmitterComponent 
  emitted_material_name="spark_blue"
  offset.x="0"
  gravity.y="-5.0"
  offset.y="0"
  count_min="70"
  count_max="140"
  x_pos_offset_min="-2"
  y_pos_offset_min="-1"
  x_pos_offset_max="2"
  y_pos_offset_max="1"
  x_vel_min="0"
  x_vel_max="0"
  y_vel_min="0"
  y_vel_max="0"
  is_trail="1"
  trail_gap="1.5"
  lifetime_min="0.4"
  lifetime_max="3.6"
  airflow_force="1.1"
  airflow_time="1.101"
  airflow_scale="0.51"
  emit_real_particles="0"
  fade_based_on_lifetime="1"
  airflow_force="3.1"
  airflow_time="1.501"
  airflow_scale="2.01"
  render_on_grid="1"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="1"
  is_emitting="1" 
></ParticleEmitterComponent>
```

-   `lifetime_min`/`lifetime_max`: `0.4`/`3.6` - Longer lifespan for these particles.
-   `airflow_force`/`airflow_time`/`airflow_scale`: These parameters control how particles are affected by air currents, contributing to their movement and spread.

## Variable Storage Component

Stores variables for use within the game's logic.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/swapper.xml"
>
</VariableStorageComponent>
```

-   `name`: `projectile_file` - The name of the variable.
-   `value_string`: `data/entities/projectiles/deck/swapper.xml` - The value, referencing its own file path.