---
title: Bounce Explosion Projectile
category: entities
---

# Bounce Explosion Projectile

This document details the configuration for the "bounce_explosion" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core of this projectile is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  ...
</Entity>
```

*   **`name`**: Set to `$projectile_default`, indicating it uses a default projectile naming convention.
*   **`tags`**: `projectile_player` signifies this projectile is associated with player actions.

## Base Projectile Configuration

The `<Base>` tag inherits properties from a standard projectile.

```xml
<Base file="data/entities/base_projectile.xml" >
  <VelocityComponent>
  </VelocityComponent> 
</Base>
```

*   **`file`**: Points to `data/entities/base_projectile.xml`, providing fundamental projectile mechanics.
*   **`VelocityComponent`**: An empty tag, suggesting velocity is managed by other components or defaults.

## Projectile Component - Key Attributes

The `<ProjectileComponent>` defines the specific behaviors and effects of this projectile.

```xml
<ProjectileComponent 
  _enabled="1" 
  lob_min="0.8"
  lob_max="1.0"
  speed_min="0"
  speed_max="0"
  die_on_low_velocity="1"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0" 
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="0"
  on_collision_die="1"
  shoot_light_flash_radius="15"
  shoot_light_flash_r="255"
  shoot_light_flash_g="10"
  shoot_light_flash_b="255"
  damage="0"
  lifetime="0" >
  ...
</ProjectileComponent>
```

*   **`_enabled`**: `1` means this component is active.
*   **`lob_min`, `lob_max`**: Set to `0.8` and `1.0` respectively, controlling the projectile's arc.
*   **`speed_min`, `speed_max`**: Both `0`, indicating the projectile doesn't have inherent speed and likely relies on initial velocity from firing.
*   **`die_on_low_velocity`**: `1` means the projectile will be destroyed if its velocity drops too low.
*   **`on_death_explode`**: `1` triggers an explosion upon death.
*   **`on_lifetime_out_explode`**: `1` triggers an explosion when the projectile's lifetime expires.
*   **`on_collision_die`**: `1` causes the projectile to die upon colliding with something.
*   **`shoot_light_flash_radius`, `shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: Define a pink light flash effect when the projectile is shot.
*   **`damage`**: `0` suggests the projectile itself does no direct damage, with damage originating from the explosion.
*   **`lifetime`**: `0` implies the projectile's existence is primarily determined by other factors like collision or velocity.

### Explosion Configuration (`config_explosion`)

This nested tag defines the properties of the explosion triggered by the projectile.

```xml
<config_explosion
  never_cache="1" 
  camera_shake="7.5" 
  explosion_radius="22" 
  explosion_sprite="data/particles/explosion_016_plasma_pink.xml"
  load_this_entity="data/entities/particles/particle_explosion/main_medium.xml"
  explosion_sprite_lifetime="0" 
  create_cell_probability="0" 
  hole_destroy_liquid="0" 
  ray_energy="90000"
  damage="1.5"
  hole_enabled="1" 
  hole_image="data/temp/explosion_hole.png" 
  particle_effect="1" 
  damage_mortals="1"
  physics_explosion_power.min="0.5" 
  physics_explosion_power.max="1.1" 
  physics_throw_enabled="1" 
  shake_vegetation="1" 
  sparks_enabled="1" 
  sparks_count_max="8" 
  sparks_count_min="5"
  spark_material="plasma_fading_pink"
  light_fade_time="0.8" 
  stains_enabled="1" 
  stains_image="data/temp/explosion_stain.png"
  audio_event_name="explosions/tnt" >
</config_explosion>
```

*   **`never_cache`**: `1` prevents caching of this explosion for performance.
*   **`camera_shake`**: `7.5` defines the intensity of camera shake.
*   **`explosion_radius`**: `22` sets the area of effect for the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_016_plasma_pink.xml` specifies the visual sprite for the explosion.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_medium.xml` loads a specific particle effect for the explosion.
*   **`ray_energy`**: `90000` indicates the energy level for any ray interactions.
*   **`damage`**: `1.5` is the damage dealt by the explosion.
*   **`hole_enabled`**: `1` enables the creation of holes in terrain.
*   **`damage_mortals`**: `1` means the explosion damages living entities.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: `0.5` to `1.1` control the force of the physics-based explosion.
*   **`shake_vegetation`**: `1` causes vegetation to shake.
*   **`sparks_enabled`**: `1` enables spark effects.
*   **`spark_material`**: `plasma_fading_pink` defines the material for the sparks.
*   **`stains_enabled`**: `1` enables explosion stains on surfaces.
*   **`audio_event_name`**: `explosions/tnt` specifies the sound effect for the explosion.

## Variable Storage Component

This component stores a reference to the projectile's own file.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/bounce_explosion.xml"
>
</VariableStorageComponent>
```

*   **`name`**: `projectile_file` is a common identifier for storing the projectile's path.
*   **`value_string`**: `data/entities/projectiles/deck/bounce_explosion.xml` is the path to this entity's XML file.