---
title: Buckshot Projectile
category: entities
---

# Buckshot Projectile

This document details the configuration of the `buckshot.xml` entity, which defines the behavior and appearance of the buckshot projectile in Noita.

## Entity Definition

The core of the buckshot projectile is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" 
   >
  <!-- ... components ... -->
</Entity>
```

## Base Projectile Configuration

The `<Base>` tag inherits properties from the default projectile entity.

```xml
<Base file="data/entities/base_projectile.xml" >
  <VelocityComponent
    air_friction="1.0"
    mass="0.06"
    >
  </VelocityComponent>
</Base>
```

### Key VelocityComponent Attributes:

*   **`air_friction`**: Controls how much air resistance affects the projectile. A value of `1.0` indicates significant air friction.
*   **`mass`**: The mass of the projectile, influencing its momentum and interaction with physics.

## Projectile Component

This is the primary component defining the buckshot's unique characteristics.

```xml
<ProjectileComponent 
  _enabled="1" 
  lob_min="0.8"
  lob_max="1.3"
  speed_min="500"
  speed_max="600"
  direction_random_rad="0.04"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0" 
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1" 
  on_collision_die="1"
  lifetime="120"
  damage="0.27"
  velocity_sets_scale="1"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0.0025"
  hit_particle_force_multiplier="0.25 "
  camera_shake_when_shot="8.0"
  create_shell_casing="1"
  shell_casing_material="plastic_red"
  bounces_left="1"
  shoot_light_flash_radius="100" 
  ragdoll_fx_on_collision="BLOOD_EXPLOSION"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_medium.xml"
  knockback_force="1.0"
  physics_impulse_coeff="2000"
  >
  <!-- ... config_explosion ... -->
</ProjectileComponent>
```

### Key ProjectileComponent Attributes:

*   **`lob_min` / `lob_max`**: Defines the minimum and maximum vertical deviation (lobbing) of the projectile.
*   **`speed_min` / `speed_max`**: Sets the range for the projectile's initial speed.
*   **`direction_random_rad`**: Introduces a small random deviation in the projectile's initial direction.
*   **`on_death_explode`**: If `1`, the projectile will explode upon death (e.g., collision or lifetime out).
*   **`on_lifetime_out_explode`**: If `1`, the projectile explodes when its lifetime expires.
*   **`on_collision_die`**: If `1`, the projectile is destroyed upon collision.
*   **`lifetime`**: The base duration (in frames) the projectile exists before expiring.
*   **`damage`**: The base damage dealt by the projectile.
*   **`create_shell_casing`**: If `1`, a shell casing is spawned when the projectile is fired.
*   **`shell_casing_material`**: Specifies the material of the spawned shell casing.
*   **`bounces_left`**: The number of times the projectile can bounce off surfaces.
*   **`camera_shake_when_shot`**: The intensity of camera shake when this projectile is fired.
*   **`ragdoll_fx_on_collision`**: The particle effect to spawn on the target when a ragdoll is hit.
*   **`muzzle_flash_file`**: Path to the particle effect used for the muzzle flash.
*   **`knockback_force`**: The force applied to entities hit by the projectile.

#### `config_explosion` Sub-attributes:

*   **`camera_shake`**: Intensity of camera shake from the explosion.
*   **`explosion_radius`**: The radius of the explosion's effect.
*   **`explosion_sprite`**: Path to the sprite used for the explosion visual.
*   **`hole_enabled`**: If `1`, the explosion creates holes in terrain.
*   **`ray_energy`**: The energy of the explosion's damaging rays.
*   **`damage`**: Damage dealt by the explosion itself (note: this is often `0.0` if the projectile's damage is the primary source).
*   **`physics_explosion_power.min` / `physics_explosion_power.max`**: The range of force applied to physics objects by the explosion.
*   **`sparks_count_min` / `sparks_count_max`**: The range for the number of sparks spawned by the explosion.
*   **`stains_enabled`**: If `1`, the explosion leaves stains on surfaces.
*   **`stains_radius`**: The radius of the stains left by the explosion.

## Sprite Component

Defines the visual representation of the projectile.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/projectiles_gfx/fireball_small.xml" 
  offset_x="2" 
  offset_y="2" 
  >
</SpriteComponent>
```

### Key SpriteComponent Attributes:

*   **`image_file`**: Path to the sprite or animation file for the projectile.
*   **`offset_x` / `offset_y`**: Adjusts the sprite's position relative to the projectile's origin.

## Light Component

Adds a light source to the projectile.

```xml
<LightComponent 
  _enabled="1" 
  radius="10" >
</LightComponent>
```

### Key LightComponent Attributes:

*   **`radius`**: The radius of the light emitted by the projectile.

## Audio Component

Handles sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="projectiles/shotgun">
</AudioComponent>
```

### Key AudioComponent Attributes:

*   **`file`**: The audio bank file containing the sound events.
*   **`event_root`**: The base event name for sounds related to this projectile.

## Variable Storage Component

Stores custom variables for the entity.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/buckshot.xml"
    >
</VariableStorageComponent>
```

### Key VariableStorageComponent Attributes:

*   **`name`**: The name of the variable.
*   **`value_string`**: The string value assigned to the variable. This is often used to reference the entity's own file path.