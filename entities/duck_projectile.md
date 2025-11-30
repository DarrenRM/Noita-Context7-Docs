---
title: Duck Projectile
category: entities
---

# Duck Projectile

This document details the configuration of the "Duck" projectile entity in Noita, primarily focusing on its behavior, visual representation, and associated effects.

## Core Components

The Duck projectile is defined by several key components that dictate its functionality:

### Base Projectile (`BaseComponent`)

Inherits fundamental projectile properties.

*   **`gravity_y`**: `120` - Controls the downward acceleration due to gravity.
*   **`mass`**: `0.065` - Affects how the projectile interacts with physics and forces.

### Projectile Behavior (`ProjectileComponent`)

This is the primary component defining the projectile's unique characteristics.

*   **`lob_min` / `lob_max`**: `0.9` / `1.0` - Defines the minimum and maximum lob angle, influencing its trajectory.
*   **`speed_min` / `speed_max`**: `250` / `280` - Sets the range for the projectile's initial launch speed.
*   **`friction`**: `0.6` - Determines how quickly the projectile loses speed over time due to air resistance.
*   **`direction_random_rad`**: `0.05` - Introduces a small amount of randomness to the projectile's initial direction.
*   **`on_death_explode`**: `1` - The projectile will explode upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile will explode when its lifetime expires.
*   **`lifetime`**: `300` - The maximum duration (in frames) the projectile exists before expiring.
*   **`lifetime_randomness`**: `100` - Adds variability to the projectile's lifetime.
*   **`damage`**: `1.6` - The base damage dealt by the projectile.
*   **`bounces_left`**: `5` - The number of times the projectile can bounce off surfaces.
*   **`bounce_always`**: `1` - The projectile will always attempt to bounce, even on shallow angles.
*   **`knockback_force`**: `1.0` - The force applied to entities upon impact.
*   **`physics_impulse_coeff`**: `4000` - A coefficient influencing the impulse applied during physics interactions.

#### Damage Types

*   **`damage_by_type`**:
    *   `fire`: `1.2` - Applies a multiplier to fire damage.

#### Explosion Configuration (`config_explosion`)

Defines the properties of the explosion when `on_death_explode` or `on_lifetime_out_explode` is triggered.

*   **`camera_shake`**: `10` - The intensity of camera shake during the explosion.
*   **`explosion_radius`**: `25` - The radius of the explosion's effect.
*   **`create_cell_probability`**: `20` - The percentage chance to create a cell upon explosion.
*   **`create_cell_material`**: `blood` - The material of the cell created.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain.
*   **`ray_energy`**: `1500000` - The energy of the destructive rays emitted by the explosion.
*   **`damage`**: `2.4` - The damage dealt by the explosion itself.
*   **`physics_explosion_power.min` / `physics_explosion_power.max`**: `0.4` / `0.65` - The range of physics force applied by the explosion.
*   **`physics_throw_enabled`**: `1` - Enables physics-based throwing of objects by the explosion.
*   **`sparks_count_min` / `sparks_count_max`**: `10` / `30` - The range for the number of sparks generated.
*   **`spark_material`**: `poo` - The material of the sparks.
*   **`stains_enabled`**: `1` - Enables the creation of impact stains.
*   **`stains_radius`**: `12` - The radius of the impact stains.
*   **`audio_event_name`**: `explosions/magic_grenade_mid` - The sound event triggered by the explosion.

### Sprite (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   **`image_file`**: `data/projectiles_gfx/duck.xml` - The path to the sprite's graphical data.
*   **`has_special_scale`**: `1` - Indicates that the sprite might have special scaling properties.

### Audio (`AudioComponent`)

Manages the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `player_projectiles/bullet_launcher` - The root event name for player projectile sounds.

### Lua Scripting (`LuaComponent`)

Integrates custom scripting for advanced behaviors.

*   **`script_source_file`**: `data/scripts/projectiles/chaotic_arc.lua`
    *   **`execute_every_n_frame`**: `2` - Executes the script every 2 frames.
*   **`script_source_file`**: `data/scripts/projectiles/duck.lua`
    *   **`_tags`**: `duck_timer` - A tag associated with this script.
    *   **`execute_every_n_frame`**: `10` - Executes the script every 10 frames.
*   **`script_source_file`**: `data/scripts/projectiles/duck_init.lua`
    *   **`execute_every_n_frame`**: `1` - Executes the script every 1 frame.
    *   **`remove_after_executed`**: `1` - The script component is removed after its first execution.

### Variable Storage (`VariableStorageComponent`)

Stores custom variables for the entity.

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/duck.xml` - Stores the entity's own file path.