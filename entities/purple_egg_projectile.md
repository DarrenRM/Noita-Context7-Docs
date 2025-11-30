---
title: Purple Egg Projectile
category: entities
---

# Purple Egg Projectile

This document describes the `egg_purple.xml` entity, which defines a purple egg projectile in Noita. It's designed to be a simple projectile with specific hatching behavior.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="100"`: Applies a moderate downward gravitational pull to the projectile.

### Projectile Component (`<ProjectileComponent>`)

Defines the specific behavior and characteristics of the purple egg projectile.

*   **`_enabled="1"`**: Ensures this component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the lobbing behavior, suggesting a relatively straight trajectory with minimal arc.
*   **`speed_min="160"`, `speed_max="170"`**: Sets the projectile's initial velocity within a narrow range.
*   **`damage="0"`**: The projectile itself deals no damage.
*   **`lifetime="19"`**: The projectile exists for 19 frames before expiring.
*   **`on_death_explode="0"`, `on_lifetime_out_explode="0"`**: The projectile does not explode upon death or when its lifetime expires.
*   **`die_on_low_velocity="0"`**: The projectile will not die simply due to losing speed.
*   **`on_collision_die="0"`**: The projectile does not die upon colliding with anything.
*   **`explosion_dont_damage_shooter="0"`**: If an explosion were to occur (which it doesn't by default), it could damage the shooter.
*   **`on_death_gfx_leave_sprite="0"`**: No graphical effects are left behind when the projectile dies.

### Variable Storage Component (`<VariableStorageComponent>`)

Used to store custom variables associated with the entity.

*   **`name="entity_list"`**: The name of the variable.
*   **`value_string="purple"`**: The string value assigned to this variable, likely used by other scripts to identify this specific entity type.

### Lua Component (`<LuaComponent>`)

This component enables custom scripting for the projectile.

*   **`script_source_file="data/scripts/items/egg_hatch.lua"`**: Links to an external Lua script responsible for the projectile's unique behavior, specifically its hatching mechanism.
*   **`execute_on_removed="1"`**: The script will execute when the entity is removed (e.g., after its lifetime expires or if it's otherwise destroyed).
*   **`execute_every_n_frame="-1"`**: The script does not execute on a regular frame interval.

### Audio Component (`<AudioComponent>`)

Handles sound effects for the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank containing the sound events.
*   **`event_root="player_projectiles/throwable"`**: Indicates the root event for sounds related to player-thrown projectiles.