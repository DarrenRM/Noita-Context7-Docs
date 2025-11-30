---
title: Laser Projectile
category: entities
---

# Laser Projectile

This document details the configuration of a standard laser projectile in Noita, focusing on its core attributes and behaviors for AI-assisted modding.

## Core Entity Configuration

The `Entity` tag defines the fundamental properties of the projectile.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player,laser"
>
  <!-- ... other components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - Indicates this entity uses a default projectile naming convention.
*   **`tags`**: `projectile_player,laser` - Essential tags for identifying this as a player-owned laser projectile.

## Base Projectile Configuration

The `Base` component inherits common projectile properties.

```xml
<Base file="data/entities/base_projectile.xml" >
  <VelocityComponent
    air_friction="-9"
    gravity_y="0"
    mass="0.04"
  >
  </VelocityComponent>
</Base>
```

*   **`VelocityComponent`**:
    *   `air_friction`: `-9` - High negative friction for rapid acceleration in air.
    *   `gravity_y`: `0` - No vertical gravity applied.
    *   `mass`: `0.04` - A very low mass, contributing to its speed.

## Projectile Component - Key Attributes

The `ProjectileComponent` governs the projectile's unique behaviors and effects.

```xml
<ProjectileComponent 
  _enabled="1" 
  lob_min="0.8"
  lob_max="1.0"
  speed_min="130"
  speed_max="150"
  friction="-12.0"
  direction_random_rad="0"
  on_death_explode="1"
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1" 
  on_collision_die="1"
  die_on_liquid_collision="1"
  lifetime="30"
  damage="0.39"
  velocity_sets_scale="1"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0.01"
  ragdoll_fx_on_collision="BLOOD_SPRAY"
  hit_particle_force_multiplier="0.25"
  camera_shake_when_shot="5.0"
  bounces_left="10"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_laser_green.xml"
  shoot_light_flash_radius="180"
  shoot_light_flash_r="120"
  shoot_light_flash_g="210"
  shoot_light_flash_b="70" 
  knockback_force="2.0"
  physics_impulse_coeff="2000"
>
  <!-- ... config_explosion ... -->
</ProjectileComponent>
```

*   **`lob_min`/`lob_max`**: `0.8` to `1.0` - Controls the projectile's initial trajectory deviation.
*   **`speed_min`/`speed_max`**: `130` to `150` - Defines the projectile's initial velocity range.
*   **`friction`**: `-12.0` - High negative friction, further increasing speed.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - Explodes when its lifetime expires.
*   **`on_collision_die`**: `1` - Dies upon colliding with an entity.
*   **`die_on_liquid_collision`**: `1` - Dies upon colliding with liquids.
*   **`lifetime`**: `30` - The duration in frames before the projectile expires.
*   **`damage`**: `0.39` - The base damage dealt by the projectile.
*   **`camera_shake_when_shot`**: `5.0` - The intensity of camera shake when this projectile is fired.
*   **`bounces_left`**: `10` - The number of bounces the projectile can perform.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_laser_green.xml` - Specifies the muzzle flash particle effect.
*   **`shoot_light_flash_radius`/`r`/`g`/`b`**: Defines the radius and color of the light flash when shot.
*   **`knockback_force`**: `2.0` - The force applied to entities upon impact.
*   **`physics_impulse_coeff`**: `2000` - Coefficient for physics impulse calculations.

### `config_explosion`

This nested tag defines the properties of the explosion that occurs when the projectile dies.

```xml
<config_explosion
  never_cache="1" 
  camera_shake="4.5" 
  explosion_radius="3"
  explosion_sprite="data/particles/explosion_016_plasma_green.xml" 
  create_cell_material="plasma_fading_green"
  create_cell_probability="15" 
  hole_enabled="1"
  ray_energy="100000"
  damage="0.22"
  hole_image="data/temp/explosion_hole.png" 
  damage_mortals="1" 
  gore_particle_count="8"
  physics_explosion_power.min="0.2" 
  physics_explosion_power.max="0.35" 
  physics_throw_enabled="1" 
  shake_vegetation="1" 
  stains_enabled="1"
  stains_radius="4" 
  light_fade_time="0.2"
  light_r="10"
  light_g="30"
  light_b="10">
</config_explosion>
```

*   **`camera_shake`**: `4.5` - Intensity of camera shake from the explosion.
*   **`explosion_radius`**: `3` - The radius of the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_016_plasma_green.xml` - The visual sprite for the explosion.
*   **`create_cell_material`**: `plasma_fading_green` - The material created by the explosion.
*   **`create_cell_probability`**: `15` - The chance (in percent) of creating a cell.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain.
*   **`ray_energy`**: `100000` - The energy of the destructive ray effect.
*   **`damage`**: `0.22` - Damage dealt by the explosion itself.
*   **`damage_mortals`**: `1` - The explosion damages living entities.
*   **`physics_explosion_power.min`/`max`**: `0.2` to `0.35` - Controls the physics force of the explosion.
*   **`stains_enabled`**: `1` - Enables the creation of stains from the explosion.
*   **`light_r`/`g`/`b`**: Defines the color of the light emitted by the explosion.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/projectiles_gfx/laser_green.xml" 
  offset_x="2" 
  offset_y="2" 
>
</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/laser_green.xml` - Specifies the sprite sheet or animation file.
*   **`offset_x`/`offset_y`**: `2` - Offsets the sprite's position.

## Light Component

Adds a light source to the projectile.

```xml
<LightComponent 
  _enabled="1" 
  radius="150" 
  r="30"
  g="90"
  b="30">
</LightComponent>
```

*   **`radius`**: `150` - The radius of the light emitted.
*   **`r`/`g`/`b`**: `30`/`90`/`30` - The color of the light (greenish hue).

## Particle Emitter Component

Generates cosmetic particles, likely for a trail effect.

```xml
<ParticleEmitterComponent 
  emitted_material_name="plasma_fading_green"
  gravity.y="0.0"
  x_vel_min="0"
  x_vel_max="0"
  y_vel_min="-2"
  y_vel_max="2"
  count_min="1"
  count_max="2"
  is_trail="1"
  trail_gap="0.5"
  lifetime_min="0.1"
  lifetime_max="0.8"
  emit_real_particles="0"
  render_on_grid="1"
  emit_cosmetic_particles="1"
  emission_interval_min_frames="1"
  emission_interval_max_frames="2"
  is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `plasma_fading_green` - The type of particle emitted.
*   **`is_trail`**: `1` - Indicates this emitter is for a trail.
*   **`trail_gap`**: `0.5` - The spacing between trail particles.
*   **`lifetime_min`/`max`**: `0.1` to `0.8` - The lifespan of emitted particles.
*   **`emit_cosmetic_particles`**: `1` - Ensures only cosmetic particles are emitted.

## Audio Component

Defines the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_laser">
</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_root`**: `player_projectiles/bullet_laser` - The specific sound event for this laser projectile.

## Variable Storage Component

Stores a reference to the projectile's own XML file.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/laser.xml"
    >
</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/deck/laser.xml` - The path to this entity's XML file.