---
title: Giga Explosion Projectile
category: entities
---

# Giga Explosion Projectile

This document details the configuration for a powerful "Giga Explosion" projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core of this projectile is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
```

*   **`name="$projectile_default"`**: Inherits default projectile properties.
*   **`tags="projectile_player"`**: Identifies this projectile as originating from the player.

### Base Projectile Configuration

The `<Base>` tag inherits common projectile behaviors.

```xml
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent>
    	</VelocityComponent> 
	</Base>
```

*   **`file="data/entities/base_projectile.xml"`**: Links to the standard projectile base entity.

### Projectile Component - Core Mechanics

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
    shoot_light_flash_g="250"
    shoot_light_flash_b="80"
	damage="0"
    lifetime="0" >
    <!-- ... config_explosion ... -->
  </ProjectileComponent>
```

**Key Attributes:**

*   **`lob_min`, `lob_max`**: Controls the projectile's arc. Values of 0.8 to 1.0 suggest a relatively straight trajectory with minimal lobbing.
*   **`speed_min`, `speed_max`**: Set to 0, indicating the projectile's speed is not directly controlled here but likely by its spawning mechanism or initial velocity.
*   **`die_on_low_velocity="1"`**: The projectile will be destroyed if its velocity drops too low.
*   **`on_death_explode="1"`**: Triggers an explosion upon the projectile's death.
*   **`on_lifetime_out_explode="1"`**: Triggers an explosion when the projectile's lifetime expires.
*   **`on_collision_die="1"`**: The projectile is destroyed upon colliding with something.
*   **`shoot_light_flash_radius`, `shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: Defines a bright yellow light flash effect when the projectile is fired.
*   **`damage="0"`**: The projectile itself deals no direct damage. Damage is handled by the explosion.
*   **`lifetime="0"`**: The projectile's lifetime is effectively infinite until other death conditions are met.

#### `config_explosion` - Explosion Parameters

This nested tag defines the properties of the explosion that occurs when the projectile dies.

```xml
    <config_explosion
      never_cache="1" 
      camera_shake="60" 
      explosion_radius="250" 
      explosion_sprite="data/particles/explosion_032.xml"
	  load_this_entity="data/entities/particles/particle_explosion/main_large.xml,data/entities/misc/explosion_was_here.xml"
      explosion_sprite_lifetime="0" 
      create_cell_probability="5" 
      hole_destroy_liquid="0" 
      hole_enabled="1" 
      ray_energy="6700000"
      damage="10"
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
	  max_durability_to_destroy="12"
      audio_event_name="explosions/nuke"
	  >
    </config_explosion>
```

**Key Attributes:**

*   **`never_cache="1"`**: Ensures this explosion effect is not cached, potentially for unique instances.
*   **`camera_shake="60"`**: The intensity of camera shake caused by the explosion.
*   **`explosion_radius="250"`**: The area of effect for the explosion.
*   **`explosion_sprite="data/particles/explosion_032.xml"`**: The visual sprite used for the explosion effect.
*   **`load_this_entity="..."`**: Specifies additional entities to load and spawn during the explosion, including particle effects and a "was here" marker.
*   **`create_cell_probability="5"`**: A probability value (likely out of 100) for creating environmental cells.
*   **`hole_enabled="1"`**: Enables the creation of holes in the environment.
*   **`ray_energy="6700000"`**: The energy value associated with the explosion's raycasting effects.
*   **`damage="10"`**: The base damage dealt by the explosion.
*   **`damage_mortals="1"`**: The explosion will damage living entities.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: The minimum and maximum force applied to physics objects by the explosion.
*   **`shake_vegetation="1"`**: Causes vegetation to shake from the explosion.
*   **`sparks_count_max`, `sparks_count_min`**: The range for the number of sparks generated.
*   **`stains_enabled="1"`, `stains_radius="35"`**: Enables and defines the radius of stains left by the explosion.
*   **`background_lightning_count="5"`**: The number of background lightning effects to spawn.
*   **`max_durability_to_destroy="12"`**: The maximum durability of objects that can be destroyed by the explosion.
*   **`audio_event_name="explosions/nuke"`**: The sound effect played for this explosion.

### Variable Storage Component

This component stores a reference to another projectile file.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/explosion.xml"
		>
	</VariableStorageComponent>
```

*   **`name="projectile_file"`**: A variable name.
*   **`value_string="data/entities/projectiles/deck/explosion.xml"`**: This indicates that when this projectile is processed, it might load or reference the `explosion.xml` projectile, suggesting a potential chain reaction or a base for this "giga" version.