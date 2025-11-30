---
title: Lightning Thunderskull Projectile
category: entities
---

# Lightning Thunderskull Projectile

This document details the configuration for the "Lightning Thunderskull" projectile entity in Noita, designed for AI-assisted modding.

## Core Components

The `lightning_thunderskull.xml` file defines a projectile with electrical properties, capable of exploding on impact or after a set duration.

### Entity Definition

```xml
<Entity 
  name="$projectile_default" >
  
  <Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
      apply_terminal_velocity="0" >
    </VelocityComponent>
  </Base>

  <!-- ... ProjectileComponent and LightningComponent ... -->

  <VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/lightning_thunderskull.xml"
    >
  </VariableStorageComponent>

</Entity>
```

*   **`name="$projectile_default"`**: Inherits default projectile properties.
*   **`Base file="data/entities/base_projectile.xml"`**: Utilizes the standard projectile base entity.
    *   **`VelocityComponent`**:
        *   `apply_terminal_velocity="0"`: Disables terminal velocity, allowing for consistent speed.

### Projectile Component

This component governs the projectile's behavior, including its speed, lifetime, and explosion on death.

```xml
<ProjectileComponent 
  _enabled="1" 
  on_death_explode="1"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="1"
  explosion_dont_damage_shooter="1"
  speed_min="500"
  speed_max="700"
  lifetime="2"
  damage="0"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_laser.xml"
  projectile_type="LIGHTNING" >
  
  <damage_by_type electricity="0.6" >
  </damage_by_type>

  <config_explosion
    never_cache="1" 
    camera_shake="7.5" 
    explosion_radius="5"
    explosion_sprite="data/particles/explosion_016.xml"
    load_this_entity="data/entities/particles/particle_explosion/main_blue_small.xml"
    explosion_sprite_lifetime="0" 
    create_cell_probability="1" 
    hole_destroy_liquid="0" 
    damage="0.6"
    hole_enabled="1" 
    hole_image="data/temp/explosion_hole.png" 
    particle_effect="1" 
    damage_mortals="1"
    physics_explosion_power.min="4" 
    physics_explosion_power.max="5" 
    physics_throw_enabled="1" 
    shake_vegetation="1" 
    sparks_count_min="1" 
    sparks_count_max="10"
    spark_material="spark_electric"
    sparks_enabled="1" 
    stains_enabled="1" 
    stains_radius="8"
    audio_enabled="0" >
  </config_explosion>
</ProjectileComponent>
```

*   **`_enabled="1"`**: Enables the component.
*   **`on_death_explode="1"`**: Triggers an explosion when the projectile is destroyed.
*   **`on_lifetime_out_explode="1"`**: Triggers an explosion when the projectile's lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: Prevents the explosion from damaging the entity that fired it.
*   **`speed_min="500"`, `speed_max="700"`**: Sets the projectile's speed range.
*   **`lifetime="2"`**: The projectile exists for 2 seconds before expiring.
*   **`damage="0"`**: Base damage of the projectile itself (before type-specific damage).
*   **`muzzle_flash_file="..."`**: Specifies the particle effect for the muzzle flash.
*   **`projectile_type="LIGHTNING"`**: Designates this as a lightning projectile.
*   **`damage_by_type electricity="0.6"`**: Applies 0.6 damage specifically of the "electricity" type.
*   **`config_explosion`**: Defines the parameters for the explosion effect.
    *   `camera_shake="7.5"`: Intensity of camera shake.
    *   `explosion_radius="5"`: The radius of the explosion.
    *   `load_this_entity="..."`: The particle entity to load for the explosion visual.
    *   `damage="0.6"`: The damage dealt by the explosion.
    *   `physics_explosion_power.min="4"`, `physics_explosion_power.max="5"`: The force applied to physics objects by the explosion.
    *   `sparks_count_min="1"`, `sparks_count_max="10"`: Number of sparks generated.
    *   `spark_material="spark_electric"`: The material used for sparks.

### Lightning Component

This component specifically handles the electrical nature of the projectile.

```xml
<LightningComponent 
  is_projectile="1"
  explosion_type="1"
  >
  <config_explosion
    never_cache="1" 
    camera_shake="7.5" 
    explosion_radius="5"
    explosion_sprite="data/particles/explosion_016.xml"
    load_this_entity="data/entities/particles/particle_explosion/main_blue.xml"
    explosion_sprite_lifetime="0" 
    create_cell_probability="1" 
    hole_destroy_liquid="0" 
    damage="0.3"
    hole_enabled="1" 
    hole_image="data/temp/explosion_hole.png" 
    particle_effect="1" 
    damage_mortals="1"
    physics_explosion_power.min="4" 
    physics_explosion_power.max="5" 
    physics_throw_enabled="1" 
    shake_vegetation="1" 
    sparks_count_min="1" 
    sparks_count_max="10"
    spark_material="spark_electric"
    sparks_enabled="1" 
    stains_enabled="1" 
    stains_radius="8"
    audio_enabled="0" >
  </config_explosion>
</LightningComponent>
```

*   **`is_projectile="1"`**: Indicates this component is associated with a projectile.
*   **`explosion_type="1"`**: Specifies the type of lightning explosion.
*   **`config_explosion`**: Similar to the `ProjectileComponent`'s explosion configuration, but potentially with different values or effects specific to the lightning aspect. Note the `damage="0.3"` here, which might be additive or override the projectile component's damage depending on game logic. The `load_this_entity` points to a different explosion particle effect (`main_blue.xml` vs `main_blue_small.xml`).

### Variable Storage Component

This component stores a reference to the projectile's own XML file, often used for internal game logic.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/lightning_thunderskull.xml"
  >
</VariableStorageComponent>
```

*   **`name="projectile_file"`**: The identifier for the stored variable.
*   **`value_string="..."`**: The path to the projectile's entity file.