---
title: Wall Square Projectile
category: entities
---

# Wall Square Projectile

This document details the configuration for the "Wall Square" projectile entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The `Wall Square` projectile is defined as a player projectile with specific behaviors and properties.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
>
  <!-- Base projectile properties -->
  <Base file="data/entities/base_projectile.xml">
    <VelocityComponent
      gravity_y="0"
      mass="0.04"
    >
    </VelocityComponent>

    <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/wall"
    >
    </AudioComponent>
  </Base>

  <!-- Projectile specific components -->
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

  <!-- Lighting effects -->
  <LightComponent
    _enabled="1"
    radius="150"
    r="30"
    g="90"
    b="30"
  >
  </LightComponent>

  <!-- Lua scripting for custom behavior -->
  <LuaComponent
    script_source_file="data/scripts/projectiles/wall_square.lua"
    execute_every_n_frame="1"
    remove_after_executed="1"
  >
  </LuaComponent>

  <!-- Variable storage for projectile identification -->
  <VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/wall_square.xml"
  >
  </VariableStorageComponent>
</Entity>
```

## Key Attributes and Elements

### `Base` Component

*   **`file`**: Specifies the base projectile XML file to inherit properties from (`data/entities/base_projectile.xml`).
*   **`VelocityComponent`**:
    *   `gravity_y`: Set to `0`, meaning no vertical gravity affects this projectile.
    *   `mass`: Set to `0.04`, indicating a very light projectile.
*   **`AudioComponent`**:
    *   `file`: Points to the audio bank (`data/audio/Desktop/projectiles.bank`).
    *   `event_root`: Defines the audio event hierarchy (`player_projectiles/wall`).

### `ProjectileComponent`

This component defines the core projectile mechanics.

*   **`_enabled`**: `1` (enabled).
*   **`lob_min`, `lob_max`**: Set to `0.8` and `1.0` respectively, suggesting a consistent, non-lobed trajectory.
*   **`speed_min`, `speed_max`**: Both `0`, indicating the projectile does not have an initial speed component from this definition.
*   **`direction_random_rad`**: `0`, meaning the projectile travels in a fixed direction.
*   **`on_death_explode`**: `0` (does not explode on death).
*   **`on_death_gfx_leave_sprite`**: `0` (does not leave a sprite on death).
*   **`on_lifetime_out_explode`**: `0` (does not explode when lifetime ends).
*   **`explosion_dont_damage_shooter`**: `1` (explosion will not harm the shooter).
*   **`on_collision_die`**: `1` (dies upon collision).
*   **`die_on_liquid_collision`**: `1` (dies upon colliding with liquids).
*   **`velocity_sets_scale`**: `1` (velocity influences scaling).
*   **`lifetime`**: `3` seconds.
*   **`damage`**: `0` (deals no direct damage).
*   **`camera_shake_when_shot`**: `5.0` (causes significant camera shake when fired).
*   **`penetrate_entities`**: `1` (can penetrate other entities).
*   **`penetrate_world`**: `1` (can penetrate world geometry).

### `LightComponent`

*   **`_enabled`**: `1` (enabled).
*   **`radius`**: `150` units.
*   **`r`, `g`, `b`**: Defines the light color (a greenish hue).

### `LuaComponent`

*   **`script_source_file`**: `data/scripts/projectiles/wall_square.lua`. This indicates custom behavior is handled by an external Lua script.
*   **`execute_every_n_frame`**: `1` (script logic runs every frame).
*   **`remove_after_executed`**: `1` (the Lua component is removed after its first execution).

### `VariableStorageComponent`

*   **`name`**: `projectile_file`.
*   **`value_string`**: `data/entities/projectiles/deck/wall_square.xml`. This serves as an identifier for the projectile's own definition file.