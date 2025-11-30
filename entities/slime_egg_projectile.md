---
title: Slime Egg Projectile
category: entities
---

---

# Slime Egg Projectile

This document describes the `egg_slime.xml` entity, which defines the behavior of a slime egg projectile in Noita.

## Key Components and Attributes

### Entity Definition

*   **name**: `$projectile_default` - Inherits base projectile properties.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

*   **VelocityComponent**:
    *   `gravity_y`: `100` - Applies a moderate downward gravitational pull.

### Projectile Component (`ProjectileComponent`)

This component governs the projectile's physical and behavioral aspects.

*   **`_enabled`**: `1` - The projectile is active.
*   **`lob_min`**: `0.8` - Minimum lob angle for projectile trajectory.
*   **`lob_max`**: `1.0` - Maximum lob angle for projectile trajectory.
*   **`speed_min`**: `160` - Minimum initial velocity.
*   **`speed_max`**: `170` - Maximum initial velocity.
*   **`on_death_explode`**: `0` - The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode`**: `0` - The projectile does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `0` - The shooter can be damaged by any potential explosion (though this projectile doesn't explode).
*   **`die_on_low_velocity`**: `0` - The projectile does not die when its velocity becomes low.
*   **`damage`**: `0` - This projectile deals no direct damage.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision.
*   **`lifetime`**: `19` - The projectile exists for 19 frames.
*   **`config_explosion`**: Empty, indicating no explosion configuration.

### Variable Storage Component (`VariableStorageComponent`)

*   **name**: `entity_list`
*   **value_string**: `slimes` - This likely tags the projectile or its effects as related to "slimes".

### Lua Component (`LuaComponent`)

This component executes a Lua script upon the projectile's removal.

*   **`execute_every_n_frame`**: `-1` - Script does not execute periodically.
*   **`execute_on_removed`**: `1` - The script runs when the projectile is removed.
*   **`script_source_file`**: `data/scripts/items/egg_hatch.lua` - This script is responsible for the projectile's behavior upon removal, likely spawning a slime.

### Audio Component (`AudioComponent`)

*   **file**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank.
*   **event_root**: `player_projectiles/throwable` - Defines the root event for projectile sounds.