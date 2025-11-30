---
title: Poison Blast Projectile
category: entities
---

# Poison Blast Projectile

This document details the configuration for the "Poison Blast" projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the projectile is defined within an `<Entity>` tag.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
>
  <!-- ... components ... -->
</Entity>
```

*   **`name`**: Set to `$projectile_default`, indicating it uses default projectile naming conventions.
*   **`tags`**: `projectile_player` signifies this projectile is fired by the player.

## Base Projectile Configuration

The projectile inherits fundamental properties from `base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml" >
  <VelocityComponent>
  </VelocityComponent>
</Base>
```

*   **`VelocityComponent`**: An empty tag here suggests that velocity is primarily managed by the `ProjectileComponent`.

## Projectile Component - Key Attributes

This component governs the projectile's behavior, including its trajectory, lifespan, and death effects.

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
  damage="0"
  on_collision_die="1"
  lifetime="0"
  shoot_light_flash_r="255"
  shoot_light_flash_g="140"
  shoot_light_flash_b="255"
  shoot_light_flash_radius="140"
>
  <!-- ... config_explosion ... -->
</ProjectileComponent>
```

**Key Attributes:**

*   **`_enabled`**: `1` means this component is active.
*   **`lob_min`, `lob_max`**: `0.8` to `1.0` suggests a relatively straight trajectory with minimal arc.
*   **`speed_min`, `speed_max`**: `0` indicates the projectile doesn't have inherent speed; it's likely dictated by the firing mechanism.
*   **`die_on_low_velocity`**: `1` means the projectile will disappear if its speed drops too low.
*   **`on_death_explode`**: `1` triggers an explosion upon death.
*   **`on_lifetime_out_explode`**: `1` triggers an explosion when the projectile's lifetime expires.
*   **`damage`**: `0` suggests the projectile itself doesn't deal direct damage, but its explosion does.
*   **`on_collision_die`**: `1` means the projectile will be destroyed upon colliding with something.
*   **`lifetime`**: `0` implies the projectile's existence is primarily determined by other factors (like collision or velocity) rather than a fixed time.
*   **`shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: `255, 140, 255` defines a pinkish light flash when the projectile is shot.
*   **`shoot_light_flash_radius`**: `140` sets the radius of this light flash.

### `config_explosion` - Explosion Details

This nested tag defines the properties of the explosion that occurs when the projectile dies.

```xml
<config_explosion
  never_cache="1"
  camera_shake="4.0"
  explosion_radius="9"
  explosion_sprite="data/particles/explosion_008.xml"
  explosion_sprite_lifetime="0"
  ray_energy="400000"
  create_cell_probability="70"
  create_cell_material="poison"
  hole_destroy_liquid="0"
  damage="0.3"
  hole_enabled="1"
  hole_image="data/temp/explosion_hole.png"
  particle_effect="1"
  damage_mortals="1"
  physics_explosion_power.min="0.4"
  physics_explosion_power.max="0.6"
  physics_throw_enabled="1"
  shake_vegetation="0"
  spark_material="poison"
  material_sparks_enabled="1"
  material_sparks_count_max="50"
  material_sparks_count_min="40"
  light_fade_time="0.8"
  stains_enabled="1"
  stains_image="data/temp/explosion_stain.png"
  audio_event_name="explosions/liquid"
>
</config_explosion>
```

**Key Explosion Attributes:**

*   **`never_cache`**: `1` prevents caching of this explosion, ensuring it's always generated fresh.
*   **`camera_shake`**: `4.0` indicates a significant camera shake effect.
*   **`explosion_radius`**: `9` defines the area of effect for the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_008.xml` specifies the visual particle effect for the explosion.
*   **`ray_energy`**: `400000` is a high value, suggesting a powerful energy release.
*   **`create_cell_probability`**: `70` means there's a 70% chance to create a new material cell.
*   **`create_cell_material`**: `poison` specifies that the created material cell will be poison.
*   **`damage`**: `0.3` is the damage dealt by the explosion itself.
*   **`hole_enabled`**: `1` enables the creation of holes in terrain.
*   **`particle_effect`**: `1` enables general particle effects for the explosion.
*   **`damage_mortals`**: `1` ensures the explosion damages living entities.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: `0.4` to `0.6` controls the force of the physics-based explosion.
*   **`physics_throw_enabled`**: `1` allows the explosion to throw physics objects.
*   **`spark_material`**: `poison` indicates that poison material sparks will be generated.
*   **`material_sparks_enabled`**: `1` enables the generation of material sparks.
*   **`material_sparks_count_min`, `material_sparks_count_max`**: `40` to `50` controls the number of material sparks.
*   **`stains_enabled`**: `1` enables the creation of stains on surfaces.
*   **`audio_event_name`**: `explosions/liquid` specifies the sound effect played for the explosion.

## Variable Storage Component

This component stores a reference to the projectile's own XML file.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/poison_blast.xml"
>
</VariableStorageComponent>
```

*   **`name`**: `projectile_file` is a common identifier for storing the projectile's asset path.
*   **`value_string`**: `data/entities/projectiles/deck/poison_blast.xml` points to the location of this entity file.