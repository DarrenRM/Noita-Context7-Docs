---
title: Water Material Projectile
category: entities
---

# Water Material Projectile

This document describes the configuration for a projectile entity in Noita, specifically designed to represent a "water" material particle. This projectile is typically spawned from a deck and has unique properties related to its behavior and interaction with the game world.

## Entity Definition

The core of this projectile is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  ...
</Entity>
```

*   **`name="$projectile_default"`**: This indicates the entity uses a default projectile name, likely to be overridden or managed by other systems.
*   **`tags="projectile_player"`**: This tag signifies that the projectile originates from the player.

### Base Projectile

The projectile inherits fundamental properties from a base projectile entity.

```xml
<Base file="data/entities/base_projectile.xml" >
</Base>
```

## Projectile Component

The `<ProjectileComponent>` defines the specific behaviors and attributes of this water projectile.

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
  on_death_particle_check_concrete="1"
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

*   **`projectile_type="MATERIAL_PARTICLE"`**: Identifies this as a material particle projectile.
*   **`lob_min="1.0"`, `lob_max="1.0"`**: Sets a fixed lob value, meaning the projectile will follow a consistent arc.
*   **`speed_min="123"`, `speed_max="135"`**: Defines the initial speed range of the projectile.
*   **`friction="3.0"`**: Controls how quickly the projectile loses velocity due to air resistance.
*   **`on_death_emit_particle="1"`**: When the projectile dies, it will emit particles.
*   **`on_death_emit_particle_type="water"`**: Specifies that the emitted particles will be of the "water" type.
*   **`on_death_particle_check_concrete="1"`**: When emitting particles on death, it checks if the surface is concrete.
*   **`die_on_liquid_collision="1"`**: The projectile will be destroyed upon colliding with any liquid.
*   **`on_collision_die="1"`**: The projectile will be destroyed upon any collision.
*   **`lifetime="360"`**: The projectile will exist for a maximum of 360 frames.
*   **`damage="0"`**: This projectile deals no direct damage.
*   **`lifetime_randomness="7"`**: Adds a small random variation to the projectile's lifetime.
*   **`camera_shake_when_shot="1.0"`**: Triggers a camera shake effect when the projectile is fired.

## Sprite Component

The `<SpriteComponent>` defines the visual representation of the projectile.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/projectiles_gfx/dirt.xml"
   >
</SpriteComponent>
```

*   **`alpha="1"`**: The sprite is fully opaque.
*   **`image_file="data/projectiles_gfx/dirt.xml"`**: This projectile uses the sprite defined in `data/projectiles_gfx/dirt.xml`. *Note: This is an interesting detail, as the sprite is named "dirt" but the projectile is for "water" material.*

## Variable Storage Component

This component stores a reference to the projectile's own XML file.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/material_water.xml"
  >
</VariableStorageComponent>
```

*   **`name="projectile_file"`**: A variable name commonly used to reference the projectile's definition.
*   **`value_string="data/entities/projectiles/deck/material_water.xml"`**: The path to this entity's XML file.