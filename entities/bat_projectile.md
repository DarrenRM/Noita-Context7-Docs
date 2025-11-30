---
title: Bat Projectile
category: entities
---

# Bat Projectile

This document details the configuration for the bat projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity is defined as a projectile, inheriting base properties from `base_projectile.xml`.

```xml
<Entity 
  name="$projectile_default" 
   >
```

## Base Projectile Properties

### Velocity Component

Defines the physical properties related to the projectile's movement.

```xml
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			mass="0.3"
			>
		</VelocityComponent>
	</Base>
```

*   **mass**: `0.3` - The mass of the projectile.

## Projectile Component

This component governs the projectile's behavior, trajectory, and interactions.

```xml
  <ProjectileComponent 
    _enabled="1" 
    lob_min="1.0"
    lob_max="1.0"
    speed_min="180"
    speed_max="200"
    angular_velocity="0"
    friction="1"
    direction_random_rad="0.02"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="1"
    ragdoll_force_multiplier="0.005"
    lifetime="100"
    camera_shake_when_shot="0"
    shoot_light_flash_radius="0"
    hit_particle_force_multiplier="0.1"
    damage="0.0"	
    velocity_sets_rotation="0"
    velocity_sets_scale="0"
    on_collision_die="1"
    on_collision_spawn_entity="1"
    spawn_entity="data/entities/animals/bat.xml"
    >
  </ProjectileComponent>
```

### Key Attributes:

*   **lob\_min/lob\_max**: `1.0` - Controls the minimum and maximum lob angle. A value of 1.0 suggests no lobbing.
*   **speed\_min/speed\_max**: `180`/`200` - The projectile's speed range.
*   **direction\_random\_rad**: `0.02` - Introduces a small random deviation in the projectile's direction.
*   **lifetime**: `100` - The duration in frames before the projectile is removed.
*   **damage**: `0.0` - The damage dealt by the projectile.
*   **on\_collision\_die**: `1` - The projectile dies upon collision.
*   **on\_collision\_spawn\_entity**: `1` - Spawns another entity upon collision.
*   **spawn\_entity**: `data/entities/animals/bat.xml` - The entity to spawn upon collision (in this case, another bat).

## Sprite Component

Defines the visual representation of the projectile.

```xml
  <SpriteComponent 
          image_file="data/enemies_gfx/bat.xml" 
          offset_x="8" 
          offset_y="14" 
          rect_animation="walk" >
  </SpriteComponent>
```

*   **image\_file**: `data/enemies_gfx/bat.xml` - Specifies the sprite sheet or animation definition.
*   **offset\_x/offset\_y**: `8`/`14` - Adjusts the sprite's position relative to the entity's origin.
*   **rect\_animation**: `walk` - Indicates the name of the animation to play.

## Audio Component

Handles the sound effects associated with the projectile.

```xml
  <AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="projectiles/slimeblob">
	</AudioComponent>
```

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **event\_root**: `projectiles/slimeblob` - The base event name for projectile sounds.