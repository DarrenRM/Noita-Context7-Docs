---
title: Wall Horizontal Projectile
category: entities
---

# Wall Horizontal Projectile

This document describes the `wall_horizontal.xml` entity, which defines a projectile used in Noita. This projectile is designed to create a horizontal wall effect upon impact.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
   >
  ...
</Entity>
```

-   **`name="$projectile_default"`**: Inherits default projectile naming conventions.
-   **`tags="projectile_player"`**: Identifies this entity as a projectile fired by the player.

## Base Projectile Configuration

The `<Base>` tag inherits properties from the general projectile template.

```xml
<Base file="data/entities/base_projectile.xml" >
  ...
</Base>
```

### Velocity Component

Controls the projectile's movement physics.

```xml
<VelocityComponent
  gravity_y="0"
  mass="0.04"
>
</VelocityComponent>
```

-   **`gravity_y="0"`**: The projectile is not affected by gravity, allowing for horizontal movement.
-   **`mass="0.04"`**: A small mass, influencing its interaction with physics.

### Audio Component

Defines the sound effects associated with this projectile.

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="player_projectiles/wall" >
</AudioComponent>
```

-   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank containing the sound events.
-   **`event_root="player_projectiles/wall"`**: Sets the root event name for player-fired wall projectiles.

## Projectile Component

This component holds the specific behaviors and properties of the `wall_horizontal` projectile.

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.8"
  lob_max="1.0"
  speed_min="0"
  speed_max="0"
  direction_random_rad="0"
  on_death_explode="0"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="0"
  explosion_dont_damage_shooter="1"
  on_collision_die="1"
  die_on_liquid_collision="1"
  velocity_sets_scale="1"
  lifetime="3"
  damage="0"
  ragdoll_force_multiplier="0.0"
  hit_particle_force_multiplier="0.0"
  camera_shake_when_shot="5.0"
  bounces_left="0"
  muzzle_flash_file=""
  shoot_light_flash_radius="1"
  knockback_force="0.0"
  physics_impulse_coeff="0"
  penetrate_entities="1"
  penetrate_world="1"
  >
  <config_explosion />
</ProjectileComponent>
```

**Key Attributes:**

-   **`_enabled="1"`**: Enables this component.
-   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the arc of the projectile. Values close to 1 suggest a very straight trajectory.
-   **`speed_min="0"`, `speed_max="0"`**: The projectile has no initial speed, implying it's likely spawned at a location and its movement is dictated by other means (e.g., Lua script).
-   **`direction_random_rad="0"`**: No random deviation in direction.
-   **`on_death_explode="0"`**: Does not explode upon death.
-   **`on_lifetime_out_explode="0"`**: Does not explode when its lifetime expires.
-   **`on_collision_die="1"`**: The projectile dies upon colliding with something.
-   **`die_on_liquid_collision="1"`**: The projectile dies upon colliding with liquids.
-   **`lifetime="3"`**: The projectile exists for 3 seconds before expiring.
-   **`damage="0"`**: Deals no direct damage.
-   **`camera_shake_when_shot="5.0"`**: Causes a moderate camera shake when fired.
-   **`penetrate_entities="1"`**: Can pass through other entities.
-   **`penetrate_world="1"`**: Can pass through the game world geometry.
-   **`<config_explosion />`**: An empty tag, indicating no explosion configuration is applied.

## Light Component

Adds a light source to the projectile.

```xml
<LightComponent
  _enabled="1"
  radius="150"
  r="30"
  g="90"
  b="30">
</LightComponent>
```

-   **`_enabled="1"`**: Enables the light component.
-   **`radius="150"`**: The radius of the light emitted.
-   **`r="30"`, `g="90"`, `b="30"`**: Defines the light color as a greenish hue.

## Lua Component

This component executes a custom Lua script to define the projectile's unique behavior.

```xml
<LuaComponent
  script_source_file="data/scripts/projectiles/wall_horizontal.lua"
  execute_every_n_frame="1"
  remove_after_executed="1"
  >
</LuaComponent>
```

-   **`script_source_file="data/scripts/projectiles/wall_horizontal.lua"`**: The path to the Lua script that governs this projectile's actions. This script is crucial for understanding how the "wall" effect is generated.
-   **`execute_every_n_frame="1"`**: The script logic runs every frame.
-   **`remove_after_executed="1"`**: The Lua component is removed after its script has executed once.

## Variable Storage Component

Stores custom variables associated with the entity.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/wall_horizontal.xml"
  >
</VariableStorageComponent>
```

-   **`name="projectile_file"`**: A variable named `projectile_file`.
-   **`value_string="data/entities/projectiles/deck/wall_horizontal.xml"`**: Stores the path to this entity's XML file, likely for internal referencing.