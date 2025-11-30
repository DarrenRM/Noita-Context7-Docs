---
title: Water Projectile
category: entities
---

# Water Projectile

This document describes the configuration for a basic water projectile entity in Noita, intended for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" 
   >
  </Entity>
```

*   **`name`**: `$projectile_default` - This indicates it uses a default projectile naming convention.

### Base Component

The projectile inherits fundamental properties from a base projectile entity.

```xml
	<Base file="data/entities/base_projectile.xml" >
	</Base>
```

### Projectile Component

This component defines the specific behaviors and physical attributes of the water projectile.

```xml
  <ProjectileComponent 
    _enabled="1" 
    projectile_type="MATERIAL_PARTICLE"
    lob_min="1.0"
    lob_max="1.0"
    speed_min="123"
    speed_max="135"
    friction="3.0"
    direction_random_rad="0.0"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="0"
    on_death_emit_particle="1"
    on_death_emit_particle_type="water"
    on_death_particle_check_concrete="0"
    explosion_dont_damage_shooter="1" 
    die_on_liquid_collision="1"
    on_collision_die="1"
    lifetime="360"
    damage="0"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.01"
    hit_particle_force_multiplier="0.25 "
    camera_shake_when_shot="1.0" 
    ground_collision_fx="0"
    ragdoll_fx_on_collision="NORMAL" >
  </ProjectileComponent>
```

**Key Attributes:**

*   **`projectile_type`**: `MATERIAL_PARTICLE` - Indicates this projectile is a material particle.
*   **`speed_min` / `speed_max`**: `123` / `135` - Defines the initial speed range of the projectile.
*   **`friction`**: `3.0` - Controls how quickly the projectile loses speed.
*   **`on_death_emit_particle`**: `1` - When the projectile dies, it will emit particles.
*   **`on_death_emit_particle_type`**: `water` - The type of particle to emit upon death.
*   **`die_on_liquid_collision`**: `1` - The projectile will be destroyed upon colliding with a liquid.
*   **`on_collision_die`**: `1` - The projectile will be destroyed upon any collision.
*   **`lifetime`**: `360` - The duration in frames before the projectile is destroyed.
*   **`damage`**: `0` - This projectile does not deal direct damage.
*   **`camera_shake_when_shot`**: `1.0` - Triggers camera shake when the projectile is fired.

### Sprite Component

This component defines the visual representation of the projectile.

```xml
  <SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/projectiles_gfx/dirt.xml" >
  </SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/dirt.xml` - Specifies the graphical asset used for the projectile. Note: This points to `dirt.xml`, which might be a placeholder or intended for a specific visual effect.

### Variable Storage Component

This component stores a variable related to the projectile's file path.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/water.xml"
		>
	</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/deck/water.xml` - The string value, indicating the path to this entity's definition.