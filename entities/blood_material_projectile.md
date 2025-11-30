---
title: Blood Material Projectile
category: entities
---

# Blood Material Projectile

This document details the configuration for a projectile entity in Noita, specifically designed to represent a "blood" material particle. This projectile is typically spawned from a deck card and has unique properties related to its material type and death behavior.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
>
  <!-- ... components ... -->
</Entity>
```

*   **`name="$projectile_default"`**: This indicates it uses a default projectile naming convention.
*   **`tags="projectile_player"`**: This tag signifies that the projectile originates from the player.

## Base Projectile Configuration

The `<Base>` component inherits common projectile properties.

```xml
<Base file="data/entities/base_projectile.xml" >
</Base>
```

*   **`file="data/entities/base_projectile.xml"`**: Links to the base projectile definition, providing fundamental projectile mechanics.

## Projectile Component - Key Attributes

The `<ProjectileComponent>` defines the specific behavior and characteristics of this blood projectile.

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
  on_death_emit_particle_type="blood"
  on_death_particle_check_concrete="1"
  explosion_dont_damage_shooter="1"
  on_death_emit_particle_count="6"
  die_on_liquid_collision="1"
  on_collision_die="1"
  lifetime="360"
  damage="0"
  velocity_sets_scale="1"
  lifetime_randomness="7"
  ragdoll_force_multiplier="0.01"
  hit_particle_force_multiplier="0.25"
  camera_shake_when_shot="1.0"
  ground_collision_fx="0"
  ragdoll_fx_on_collision="NORMAL"
>
</ProjectileComponent>
```

**Key Attributes:**

*   **`projectile_type="MATERIAL_PARTICLE"`**: Identifies this as a projectile that carries a material.
*   **`speed_min="123"`, `speed_max="135"`**: Sets the initial velocity range of the projectile.
*   **`friction="3.0"`**: Controls how quickly the projectile loses speed.
*   **`on_death_emit_particle="1"`**: Enables particle emission upon death.
*   **`on_death_emit_particle_type="blood"`**: Specifies that the emitted particles will be of the "blood" type.
*   **`on_death_emit_particle_count="6"`**: Determines the number of blood particles to emit on death.
*   **`die_on_liquid_collision="1"`**: Causes the projectile to be destroyed upon contact with liquids.
*   **`on_collision_die="1"`**: Makes the projectile die on any collision.
*   **`lifetime="360"`**: Sets the maximum duration the projectile exists in seconds.
*   **`damage="0"`**: This projectile deals no direct damage.
*   **`camera_shake_when_shot="1.0"`**: Triggers camera shake when this projectile is fired.

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

*   **`image_file="data/projectiles_gfx/dirt.xml"`**: This is notable as it uses the sprite definition for "dirt" projectiles, suggesting a visual similarity or a placeholder.

## Variable Storage Component

This component stores a reference to the projectile's own definition file.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/material_blood.xml"
>
</VariableStorageComponent>
```

*   **`name="projectile_file"`**: A variable name commonly used to reference the projectile's XML file.
*   **`value_string="data/entities/projectiles/deck/material_blood.xml"`**: The path to this specific projectile's definition.