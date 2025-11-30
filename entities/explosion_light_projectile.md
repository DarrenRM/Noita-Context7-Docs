---
title: Explosion Light Projectile
category: entities
---

# Explosion Light Projectile

This document details the configuration for a projectile entity in Noita, specifically designed to create a light-based explosion upon death or collision.

## Entity Definition

The core of this projectile is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  ...
</Entity>
```

*   **`name`**: `$projectile_default` - Indicates this entity uses a default projectile naming convention.
*   **`tags`**: `projectile_player` - This projectile is associated with the player's actions.

## Base Projectile Configuration

It inherits fundamental projectile properties from `base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent>
    </VelocityComponent> 
</Base>
```

*   **`VelocityComponent`**: An empty tag, suggesting velocity properties are managed elsewhere or default to standard behavior.

## Projectile Component - Core Functionality

This component defines the projectile's behavior, particularly its explosive nature and light effects.

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
  ...
</ProjectileComponent>
```

**Key Attributes:**

*   **`_enabled`**: `1` - The component is active.
*   **`lob_min`, `lob_max`**: `0.8`, `1.0` - Controls the projectile's lobbing behavior, suggesting a relatively straight trajectory.
*   **`speed_min`, `speed_max`**: `0`, `0` - The projectile has no initial speed, implying it might be spawned with velocity or its speed is negligible.
*   **`die_on_low_velocity`**: `1` - The projectile will be destroyed if its velocity drops too low.
*   **`on_death_explode`**: `1` - Triggers an explosion when the projectile dies.
*   **`on_lifetime_out_explode`**: `1` - Triggers an explosion when its lifetime expires.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon colliding with something.
*   **`shoot_light_flash_radius`**: `15` - The radius of the light flash when the projectile is fired.
*   **`shoot_light_flash_r`, `g`, `b`**: `255`, `250`, `80` - Defines the color of the light flash (yellowish-white).
*   **`damage`**: `0` - The projectile itself deals no direct damage. Damage is handled by the explosion.
*   **`lifetime`**: `0` - The projectile has no inherent lifetime, likely meaning it persists until it collides or its velocity drops.

### `config_explosion` - Explosion Details

This nested tag defines the parameters of the explosion that occurs.

```xml
    <config_explosion
      never_cache="1" 
      camera_shake="7.5" 
      explosion_radius="35" 
      explosion_sprite="data/particles/explosion_040_poof.xml"
	  load_this_entity="data/entities/particles/particle_explosion/main_medium.xml"
      explosion_sprite_lifetime="0" 
      create_cell_probability="20" 
      create_cell_material="fire" 
      hole_destroy_liquid="0" 
	  ray_energy="1000"
	  max_durability_to_destroy="2"
      damage="3.75"
      hole_enabled="1" 
      hole_image="data/temp/explosion_hole.png" 
      particle_effect="1" 
      damage_mortals="1"
	  physics_explosion_power.min="1.0" 
      physics_explosion_power.max="1.5" 
      physics_throw_enabled="1" 
      shake_vegetation="1" 
      sparks_enabled="1" 
      sparks_count_max="50" 
      sparks_count_min="40"
      light_fade_time="0.8" 
      stains_enabled="1" 
      stains_image="data/temp/explosion_stain.png"
     audio_event_name="explosions/tnt" >
    </config_explosion>
```

**Key Attributes:**

*   **`never_cache`**: `1` - Ensures this explosion configuration is not cached, potentially for dynamic effects.
*   **`camera_shake`**: `7.5` - The intensity of camera shake caused by the explosion.
*   **`explosion_radius`**: `35` - The area of effect for the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_040_poof.xml` - The visual particle effect used for the explosion.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_medium.xml` - An entity to load for the explosion's visual representation.
*   **`create_cell_probability`**: `20` - The percentage chance (20%) of creating a new material cell.
*   **`create_cell_material`**: `fire` - The material created when a new cell is formed.
*   **`ray_energy`**: `1000` - The energy value for any light rays emitted by the explosion.
*   **`max_durability_to_destroy`**: `2` - The maximum durability of objects that can be destroyed by the explosion.
*   **`damage`**: `3.75` - The damage dealt by the explosion to entities.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain.
*   **`particle_effect`**: `1` - Enables general particle effects for the explosion.
*   **`damage_mortals`**: `1` - The explosion damages living entities.
*   **`physics_explosion_power.min`, `.max`**: `1.0`, `1.5` - The minimum and maximum force applied to physics objects.
*   **`physics_throw_enabled`**: `1` - Objects affected by the explosion can be thrown.
*   **`shake_vegetation`**: `1` - Causes vegetation to shake.
*   **`sparks_enabled`**: `1` - Enables sparks to be generated.
*   **`sparks_count_min`, `max`**: `40`, `50` - The range for the number of sparks generated.
*   **`light_fade_time`**: `0.8` - How long the explosion's light effect takes to fade.
*   **`stains_enabled`**: `1` - Enables explosion stains on surfaces.
*   **`audio_event_name`**: `explosions/tnt` - The sound effect played for the explosion.

## Variable Storage Component

This component stores a reference to another projectile entity.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/explosion.xml"
		>
	</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - Identifies the variable.
*   **`value_string`**: `data/entities/projectiles/deck/explosion.xml` - Points to another projectile definition, likely for a more complex or standard explosion effect.