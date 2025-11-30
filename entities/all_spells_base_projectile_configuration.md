---
title: All Spells Base Projectile Configuration
category: entities
---

# All Spells Base Projectile Configuration

This document details the base configuration for projectiles used by all spells in Noita, as defined in `all_spells_base.xml`. This entity serves as a foundational template, with many attributes being overridden or extended by specific spell projectile configurations.

## Core Entity Properties

*   **`name`**: `$projectile_default` - A placeholder name, indicating this is a base entity.
*   **`tags`**: `all_spells_base` - Identifies this entity as the base for all spell projectiles.

## Base Projectile Component (`Base file="data/entities/base_projectile.xml"`)

This section inherits and configures fundamental projectile physics.

### Velocity Component

*   **`gravity_y`**: `0` - The projectile experiences no vertical gravity.
*   **`air_friction`**: `0` - The projectile is not affected by air resistance.

## Projectile Component (`ProjectileComponent`)

This component defines the core behavior and properties of the projectile.

### Key Attributes

*   **`_enabled`**: `1` - Ensures this component is active.
*   **`lob_min`**: `0.8` - Minimum lob angle for projectile trajectory.
*   **`lob_max`**: `1.0` - Maximum lob angle for projectile trajectory.
*   **`speed_min`**: `0` - Minimum initial speed.
*   **`speed_max`**: `0` - Maximum initial speed. (Often overridden by specific spells).
*   **`die_on_low_velocity`**: `0` - The projectile does not die if its velocity drops too low.
*   **`on_death_explode`**: `0` - The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No graphical effects are left behind when the projectile dies.
*   **`on_lifetime_out_explode`**: `0` - The projectile does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - If an explosion occurs, it will not damage the entity that fired it.
*   **`penetrate_entities`**: `1` - The projectile can pass through other entities.
*   **`penetrate_world`**: `1` - The projectile can pass through the game world geometry.
*   **`damage`**: `0.15` - Base damage value. This is often a very low value for the base and is significantly increased by specific spell configurations.
*   **`on_collision_die`**: `0` - The projectile does not die upon colliding with an entity or the world.
*   **`lifetime`**: `250` - The projectile's lifespan in frames.

## Lua Component (`LuaComponent`)

This component links to a Lua script responsible for initializing spell projectile behavior.

*   **`script_source_file`**: `data/scripts/projectiles/all_spells_init.lua` - The script executed when the projectile is added.
*   **`remove_after_executed`**: `1` - The Lua component is removed after its script has run.
*   **`execute_on_added`**: `1` - The script is executed immediately when the projectile is created.

## Audio Component (`AudioComponent`)

This component defines the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `player_projectiles/all_spell` - The root event name for sounds related to this projectile type.