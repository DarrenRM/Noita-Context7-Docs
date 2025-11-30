---
title: Projectile - Dirt Material Particle
category: entities
---

# Projectile - Dirt Material Particle

This document details the configuration for a projectile entity in Noita, specifically designed to represent a "dirt" material particle. This projectile is typically spawned from a deck and is used for its material properties rather than direct damage.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  </Entity>
```

*   **`name="$projectile_default"`**: This indicates the entity uses a default projectile name, likely to be overridden by specific spawning logic.
*   **`tags="projectile_player"`**: This tag signifies that the projectile originates from the player.

## Base Projectile Configuration

The `<Base>` tag inherits properties from a common projectile template.

```xml
<Base file="data/entities/base_projectile.xml" >
</Base>
```

*   **`file="data/entities/base_projectile.xml"`**: This points to the shared configuration file for most projectiles, providing a foundation for common behaviors.

## Projectile Component - Key Attributes

The `<ProjectileComponent>` defines the specific behavior and properties of this dirt projectile.

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
  on_death_emit_particle_type="soil"
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

*   **`projectile_type="MATERIAL_PARTICLE"`**: Crucially defines this as a material particle, impacting how it interacts with the game world.
*   **`speed_min="123"`, `speed_max="135"`**: Sets the initial velocity range for the projectile.
*   **`friction="3.0"`**: Determines how quickly the projectile loses speed due to air resistance or other factors.
*   **`on_death_emit_particle="1"`**: When the projectile dies (e.g., on collision or lifetime expiry), it will emit particles.
*   **`on_death_emit_particle_type="soil"`**: Specifies that the emitted particles will be of the "soil" type.
*   **`on_death_particle_check_concrete="1"`**: When emitting particles on death, it checks if the collision surface is concrete.
*   **`die_on_liquid_collision="1"`**: The projectile will be destroyed upon colliding with any liquid.
*   **`on_collision_die="1"`**: The projectile will be destroyed upon colliding with any solid object.
*   **`lifetime="360"`**: The projectile will exist for a maximum of 360 frames before expiring.
*   **`damage="0"`**: This projectile deals no direct damage.
*   **`camera_shake_when_shot="1.0"`**: A moderate camera shake effect is applied when this projectile is fired.

## Sprite Component - Visual Representation

The `<SpriteComponent>` defines the visual appearance of the projectile.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/projectiles_gfx/dirt.xml"
   >
</SpriteComponent>
```

*   **`image_file="data/projectiles_gfx/dirt.xml"`**: Links to an external XML file that defines the sprite's animation and visual assets for dirt.

## Variable Storage Component

This component stores a reference to the projectile's own entity file.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/material_dirt.xml"
  >
</VariableStorageComponent>
```

*   **`name="projectile_file"`**: A common variable name used to identify the projectile's source file.
*   **`value_string="data/entities/projectiles/deck/material_dirt.xml"`**: The path to this specific entity file.