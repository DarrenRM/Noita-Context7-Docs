---
title: Thunderburst Thundermage Projectile
category: entities
---

# Thunderburst Thundermage Projectile

This document details the configuration for the "Thunderburst Thundermage" projectile in Noita, focusing on its behavior and effects.

## Entity Definition

The core of this projectile is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" 
   >
  ...
</Entity>
```

## Base Projectile Configuration

It inherits fundamental projectile properties from `base_projectile.xml`.

```xml
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent>
    	</VelocityComponent> 
	</Base>
```

## Projectile Component

This component governs the projectile's specific behaviors and interactions.

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
    lifetime="2" >
    ...
  </ProjectileComponent>
```

### Key Projectile Attributes:

*   **`lob_min`, `lob_max`**: Controls the projectile's lobbing arc. Values between 0.8 and 1.0 suggest a relatively straight trajectory with minimal arc.
*   **`speed_min`, `speed_max`**: Set to 0, indicating the projectile's initial speed is not directly controlled here and likely determined by its spawning entity.
*   **`die_on_low_velocity`**: Set to `1`, meaning the projectile will be destroyed if its velocity drops too low.
*   **`on_death_explode`**: Set to `1`, causing an explosion upon the projectile's death.
*   **`on_lifetime_out_explode`**: Set to `1`, causing an explosion when the projectile's `lifetime` expires.
*   **`damage`**: Initial damage of the projectile itself is `0`. Damage is primarily dealt by the explosion.
*   **`on_collision_die`**: Set to `1`, the projectile is destroyed upon colliding with something.
*   **`lifetime`**: The projectile exists for `2` seconds before expiring and potentially exploding.

### Explosion Configuration (`config_explosion`)

This nested tag defines the properties of the explosion triggered by the projectile.

```xml
    <config_explosion
      never_cache="1" 
      camera_shake="30.5" 
      explosion_radius="15" 
      explosion_sprite="data/particles/explosion_016_plasma.xml"
	  load_this_entity="data/entities/misc/loose_ground.xml"
      explosion_sprite_lifetime="0.5" 
	  ray_energy="70000"
      create_cell_probability="0" 
      create_cell_material="fire"
	  explosion_sprite_emissive="1"
	  explosion_sprite_additive="1"
      hole_destroy_liquid="0" 
	  particle_effect="0"
      damage="2.5"
      hole_enabled="1" 
      hole_image="data/temp/explosion_hole.png" 
      particle_effect="1" 
      damage_mortals="1"
	  physics_explosion_power.min="1.5"
      physics_explosion_power.max="2.6" 
      physics_throw_enabled="1" 
      shake_vegetation="0" 
	  spark_material="spark_blue"
      sparks_enabled="1" 
      sparks_count_max="30" 
      sparks_count_min="20"
      light_fade_time="0.8" 
      stains_enabled="1" 
      stains_image="data/temp/explosion_stain.png"
      audio_event_name="explosions/electric_small" >
    </config_explosion>
```

#### Key Explosion Attributes:

*   **`camera_shake`**: `30.5` - A significant camera shake effect.
*   **`explosion_radius`**: `15` - The area of effect for the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_016_plasma.xml` - The visual effect used for the explosion.
*   **`load_this_entity`**: `data/entities/misc/loose_ground.xml` - An entity to spawn upon explosion, likely for ground destruction effects.
*   **`ray_energy`**: `70000` - High energy value, suggesting a powerful electrical or plasma-like effect.
*   **`damage`**: `2.5` - The damage dealt by the explosion.
*   **`hole_enabled`**: `1` - Creates holes in surfaces.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: `1.5` to `2.6` - The force of the physics-based explosion.
*   **`sparks_enabled`**: `1` - Sparks are generated.
*   **`spark_material`**: `spark_blue` - The material used for the sparks.
*   **`audio_event_name`**: `explosions/electric_small` - The sound effect played upon explosion.

## Lua Component

This component links the projectile to a Lua script for custom behavior.

```xml
  <LuaComponent
	execute_on_removed="1"
    execute_every_n_frame="-1"
    script_source_file="data/scripts/projectiles/lightning_explosion_thundermage.lua"
    remove_after_executed="0">
  </LuaComponent>
```

### Key Lua Component Attributes:

*   **`execute_on_removed`**: `1` - The script will execute when the entity is removed.
*   **`script_source_file`**: `data/scripts/projectiles/lightning_explosion_thundermage.lua` - The path to the associated Lua script. This script likely handles the specific "thunderburst" effects beyond the basic explosion.

## Variable Storage Component

Stores a reference to the projectile's own XML file.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/thunderburst_thundermage.xml"
		>
	</VariableStorageComponent>
```