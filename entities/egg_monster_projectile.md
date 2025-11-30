---
title: Egg Monster Projectile
category: entities
---

# Egg Monster Projectile

This document describes the `egg_monster.xml` entity, which defines the behavior of a projectile that hatches into a monster.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`gravity_y`**: `100` - Applies a downward gravitational force to the projectile.

### Projectile Component (`<ProjectileComponent>`)

Defines the specific characteristics of this projectile.

*   **`_enabled`**: `1` - Enables this component.
*   **`lob_min`**: `0.8` - Minimum lob angle for projectile trajectory.
*   **`lob_max`**: `1.0` - Maximum lob angle for projectile trajectory.
*   **`speed_min`**: `160` - Minimum initial speed of the projectile.
*   **`speed_max`**: `170` - Maximum initial speed of the projectile.
*   **`damage`**: `0` - This projectile does not deal direct damage.
*   **`lifetime`**: `19` - The projectile will exist for 19 frames before expiring.
*   **`on_death_explode`**: `0` - The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode`**: `0` - The projectile does not explode when its lifetime expires.
*   **`die_on_low_velocity`**: `0` - The projectile does not die when its velocity becomes low.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision.

### Variable Storage Component (`<VariableStorageComponent>`)

Stores variables associated with the entity.

*   **`name`**: `entity_list`
*   **`value_string`**: `monsters` - This likely indicates that the projectile is intended to interact with or spawn entities from the "monsters" category.

### Lua Component (`<LuaComponent>`)

Executes Lua scripts for custom behavior.

*   **`script_source_file`**: `data/scripts/items/egg_hatch.lua` - This script is executed when the projectile is removed (e.g., after its lifetime expires or potentially on collision if `on_collision_die` were enabled). This script is responsible for the "egg hatching" functionality.
*   **`execute_on_removed`**: `1` - The script will execute when the entity is removed.
*   **`execute_every_n_frame`**: `-1` - The script does not execute periodically.

### Audio Component (`<AudioComponent>`)

Handles sound effects for the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank file.
*   **`event_root`**: `player_projectiles/throwable` - Defines the root event for projectile sounds.