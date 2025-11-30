---
title: Hidden Shot Projectile
category: entities
---

---

# Hidden Shot Projectile

This document details the configuration of the "hiddenshot" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity definition for the hidden shot projectile.

```xml
<Entity 
  name="$projectile_default" 
  tags="resist_repulsion"
>
  <!-- ... components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - Indicates this is a default projectile type.
*   **`tags`**: `resist_repulsion` - The projectile resists repulsion forces.

## Base Projectile Component

Inherits fundamental projectile behavior.

```xml
<Base file="data/entities/base_projectile.xml">
  <VelocityComponent
    gravity_y="0"
    air_friction="0"
    mass="0.05"
  >
  </VelocityComponent>
</Base>
```

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: No vertical gravity applied.
    *   `air_friction="0"`: No air friction.
    *   `mass="0.05"`: Low mass for the projectile.

## Projectile Component

Defines the specific behavior and effects of the hidden shot.

```xml
<ProjectileComponent 
  _enabled="1" 
  lob_min="0.8"
  lob_max="1.0"
  speed_min="500"
  speed_max="500"
  die_on_low_velocity="0"
  on_death_explode="1"
  on_death_gfx_leave_sprite="0" 
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1"
  damage="0.3"
  on_collision_die="1"
  lifetime="8"
  knockback_force="1.0"
>
  <!-- ... damage_by_type, config_explosion ... -->
</ProjectileComponent>
```

*   **`lob_min`, `lob_max`**: `0.8` to `1.0` - Controls the projectile's lobbing behavior.
*   **`speed_min`, `speed_max`**: `500` - Constant speed for the projectile.
*   **`die_on_low_velocity`**: `0` - Does not die when velocity becomes low.
*   **`on_death_explode`**: `1` - Explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - Explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion does not damage the entity that fired it.
*   **`damage`**: `0.3` - Base damage dealt by the projectile.
*   **`on_collision_die`**: `1` - Dies upon collision.
*   **`lifetime`**: `8` - The projectile exists for 8 seconds.
*   **`knockback_force`**: `1.0` - The force applied for knockback.

### Damage by Type

Specifies damage multipliers for different damage types.

```xml
<damage_by_type
  fire="0.3"
  slice="0.3"
  radioactive="0.3"
>
</damage_by_type>
```

*   Applies a `0.3` multiplier for fire, slice, and radioactive damage.

### Config Explosion

Details the explosion effect upon the projectile's death.

```xml
<config_explosion
  never_cache="1" 
  camera_shake="0" 
  explosion_radius="12" 
  explosion_sprite="data/particles/explosion_016_plasma.xml" 
  explosion_sprite_lifetime="0.0" 
  create_cell_probability="0" 
  ray_energy="5000"
  hole_destroy_liquid="0" 
  hole_enabled="0" 
  explosion_sprite_emissive="1"
  explosion_sprite_additive="1"
  particle_effect="0" 
  damage_mortals="0"
  physics_explosion_power.min="0.13" 
  physics_explosion_power.max="0.23" 
  physics_throw_enabled="1" 
  shake_vegetation="1" 
  sparks_enabled="1" 
  sparks_count_max="20" 
  sparks_count_min="40"
  light_fade_time="0.8" 
  spark_material="plasma_fading"
  light_r="15"
  light_g="15"
  light_b="40"
  stains_enabled="0" 
  audio_enabled="0" 
>
</config_explosion>
```

*   **`never_cache`**: `1` - Prevents caching of this explosion.
*   **`camera_shake`**: `0` - No camera shake on explosion.
*   **`explosion_radius`**: `12` - The radius of the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_016_plasma.xml` - The visual effect for the explosion.
*   **`ray_energy`**: `5000` - Energy value for ray interactions.
*   **`hole_enabled`**: `0` - No terrain destruction holes are created.
*   **`explosion_sprite_emissive`**: `1` - The explosion sprite is emissive.
*   **`explosion_sprite_additive`**: `1` - The explosion sprite uses additive blending.
*   **`damage_mortals`**: `0` - The explosion does not damage mortals.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: `0.13` to `0.23` - Controls the physics force of the explosion.
*   **`physics_throw_enabled`**: `1` - Enables physics-based throwing from the explosion.
*   **`shake_vegetation`**: `1` - Vegetation is affected by the explosion.
*   **`sparks_enabled`**: `1` - Sparks are generated.
*   **`sparks_count_min`, `sparks_count_max`**: `40` to `20` - Number of sparks.
*   **`light_r`, `light_g`, `light_b`**: `15`, `15`, `40` - Defines the RGB color of the explosion light.
*   **`audio_enabled`**: `0` - No explosion sound is played.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/projectiles_gfx/orb_blue.xml" 
  offset_x="6" 
  offset_y="6" 
  rect_animation="spawn" 
  emissive="1"
  additive="1"
  update_transform_rotation="0"
>
</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/orb_blue.xml` - The sprite image used.
*   **`offset_x`, `offset_y`**: `6` - Offsets the sprite's position.
*   **`rect_animation`**: `spawn` - Uses the "spawn" animation from the sprite sheet.
*   **`emissive`**: `1` - The sprite is emissive.
*   **`additive`**: `1` - The sprite uses additive blending.
*   **`update_transform_rotation`**: `0` - The sprite does not update its rotation with the projectile's transform.

There are two identical `SpriteComponent` entries, likely for layering or different animation states.

## Light Component

Adds a light source to the projectile.

```xml
<LightComponent 
  _enabled="1" 
  radius="150" 
  r="130"
  g="35"
  b="90">
</LightComponent>
```

*   **`radius`**: `150` - The radius of the light.
*   **`r`, `g`, `b`**: `130`, `35`, `90` - Defines the RGB color of the light.

## Audio Component

Specifies the sound bank and event for the projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="projectiles/orb_c" >
</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   **`event_root`**: `projectiles/orb_c` - The root event for projectile sounds.

## Variable Storage Component

Stores custom variables for the entity.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/hiddenshot.xml"
>
</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/hiddenshot.xml` - The string value, likely referencing its own file path.