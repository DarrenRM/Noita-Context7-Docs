---
title: Enlightened Laser Electric Beam Projectile
category: entities
---

# Enlightened Laser Electric Beam Projectile

This document details the configuration for the "enlightened_laser_elecbeam" projectile in Noita, focusing on its core attributes for AI-assisted modding.

## Core Entity Configuration

The projectile is defined as an entity with a base projectile component, a lightning component, and a variable storage component.

```xml
<Entity 
  name="$projectile_default" >
  
  <!-- Base projectile properties -->
  <Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
      apply_terminal_velocity="0" >
    </VelocityComponent>
  </Base>

  <!-- Projectile-specific settings -->
  <ProjectileComponent 
    _enabled="1" 
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="1"
    lifetime="3"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_laser.xml"
    projectile_type="LIGHTNING" >
    <damage_by_type electricity="1.0" >
    </damage_by_type>
  </ProjectileComponent>
  
  <!-- Lightning effect configuration -->
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
  
  <!-- Variable storage for projectile identification -->
  <VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/enlightened_laser_elecbeam.xml"
		>
	</VariableStorageComponent>

</Entity>
```

### Key Attributes:

#### `<ProjectileComponent>`

*   **`lifetime`**: `3` - The duration in seconds the projectile exists before expiring.
*   **`projectile_type`**: `"LIGHTNING"` - Specifies the projectile's elemental type, influencing its behavior and interactions.
*   **`on_death_explode`**: `"1"` - The projectile will explode upon death (e.g., hitting a target or expiring).
*   **`explosion_dont_damage_shooter`**: `"1"` - Prevents the projectile's explosion from harming the entity that fired it.
*   **`muzzle_flash_file`**: `"data/entities/particles/muzzle_flashes/muzzle_flash_laser.xml"` - The particle effect used for the muzzle flash when the projectile is fired.
*   **`damage_by_type electricity="1.0"`**: Defines the damage dealt by the projectile, specifically `1.0` electricity damage.

#### `<LightningComponent>`

*   **`is_projectile`**: `"1"` - Indicates this lightning component is associated with a projectile.
*   **`explosion_type`**: `"1"` - A numerical identifier for the type of lightning explosion.

#### `<config_explosion>` (within `<LightningComponent>`)

*   **`camera_shake`**: `7.5` - The intensity of camera shake caused by the explosion.
*   **`explosion_radius`**: `5` - The radius of the explosion effect.
*   **`explosion_sprite`**: `"data/particles/explosion_016.xml"` - The sprite used for the explosion visual.
*   **`load_this_entity`**: `"data/entities/particles/particle_explosion/main_blue.xml"` - The entity to load for the main explosion particle effect.
*   **`hole_enabled`**: `"1"` - Enables the creation of holes in the environment upon explosion.
*   **`hole_image`**: `"data/temp/explosion_hole.png"` - The image used for the explosion hole.
*   **`physics_explosion_power.min`**: `4` - The minimum physics force applied by the explosion.
*   **`physics_explosion_power.max`**: `5` - The maximum physics force applied by the explosion.
*   **`sparks_enabled`**: `"1"` - Enables the spawning of sparks from the explosion.
*   **`spark_material`**: `"spark_electric"` - The material used for the spawned sparks.
*   **`stains_enabled`**: `"1"` - Enables the creation of stains on surfaces from the explosion.
*   **`stains_radius`**: `8` - The radius of the stains created.

#### `<VariableStorageComponent>`

*   **`name`**: `"projectile_file"` - Identifies this component as storing a file path.
*   **`value_string`**: `"data/entities/projectiles/enlightened_laser_elecbeam.xml"` - The actual file path of this projectile entity, useful for referencing.