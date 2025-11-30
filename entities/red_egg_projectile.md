---
title: Red Egg Projectile
category: entities
---

# Red Egg Projectile

This document details the configuration for the "red egg" projectile entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Entity Definition

The core entity definition for the red egg projectile.

```xml
<Entity 
  name="$projectile_default" 
   >
  </Entity>
```

## Base Projectile Configuration

Inherits fundamental projectile properties from `base_projectile.xml`.

### Velocity Component

Controls the projectile's movement in relation to gravity.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="100">
    </VelocityComponent> 
</Base>
```

*   **`gravity_y`**: The force of gravity applied to the projectile along the Y-axis. A value of `100` indicates a moderate downward pull.

## Projectile Component

Defines specific behaviors and characteristics of the red egg projectile.

```xml
<ProjectileComponent 
    _enabled="1" 
    lob_min="0.8"
    lob_max="1.0"
    speed_min="160"
    speed_max="170"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="0"
    die_on_low_velocity="0"
    damage="0"
    on_collision_die="0"
    lifetime="19" >
    <config_explosion>
    </config_explosion>
</ProjectileComponent>
```

*   **`_enabled`**: Whether this component is active (`1`) or not (`0`).
*   **`lob_min` / `lob_max`**: Defines the minimum and maximum lobbing behavior (arc of the projectile). Values are between 0 and 1.
*   **`speed_min` / `speed_max`**: The range of initial speeds for the projectile.
*   **`on_death_explode`**: If the projectile should explode upon death (`1`) or not (`0`).
*   **`on_death_gfx_leave_sprite`**: If graphical effects should be left behind upon death.
*   **`on_lifetime_out_explode`**: If the projectile should explode when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: If the explosion should not damage the entity that fired it.
*   **`die_on_low_velocity`**: If the projectile should die when its velocity drops below a certain threshold.
*   **`damage`**: The amount of damage the projectile deals. `0` means it deals no direct damage.
*   **`on_collision_die`**: If the projectile should die upon collision with another entity.
*   **`lifetime`**: The duration in frames before the projectile is destroyed.

## Variable Storage Component

Stores custom variables associated with the entity.

```xml
<VariableStorageComponent
    name="entity_list"
    value_string="red"
/>
```

*   **`name`**: The name of the variable.
*   **`value_string`**: The string value assigned to the variable. Here, it's used to identify the egg type as "red".

## Lua Component

Attaches a Lua script to the entity for custom logic.

```xml
<LuaComponent
    execute_every_n_frame="-1"
    execute_on_removed="1"
    script_source_file="data/scripts/items/egg_hatch.lua"
    >
</LuaComponent>
```

*   **`execute_every_n_frame`**: How often the script executes. `-1` typically means it runs only when triggered by other events.
*   **`execute_on_removed`**: If the script should execute when the entity is removed. `1` means it will.
*   **`script_source_file`**: The path to the Lua script file that controls the entity's behavior. In this case, `egg_hatch.lua` suggests it handles the hatching logic for the egg.

## Audio Component

Defines the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/throwable">
</AudioComponent>
```

*   **`file`**: The audio bank file containing the sound events.
*   **`event_root`**: The root event name within the audio bank for this projectile's sounds.