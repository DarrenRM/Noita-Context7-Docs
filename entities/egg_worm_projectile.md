---
title: Egg Worm Projectile
category: entities
---

---

# Egg Worm Projectile

This document describes the `egg_worm.xml` entity, which defines the behavior of the Egg Worm projectile in Noita.

## Key Components and Attributes

### Entity Definition

*   **name**: `$projectile_default` - Inherits base projectile properties.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

*   **VelocityComponent**:
    *   **gravity\_y**: `100` - Applies a downward gravitational force.

### Projectile Component (`ProjectileComponent`)

This component governs the projectile's physical and behavioral characteristics.

*   **_enabled**: `1` - Enables the projectile.
*   **lob\_min**: `0.8` - Minimum lobbing factor.
*   **lob\_max**: `1.0` - Maximum lobbing factor.
*   **speed\_min**: `160` - Minimum projectile speed.
*   **speed\_max**: `170` - Maximum projectile speed.
*   **on\_death\_explode**: `0` - Does not explode upon death.
*   **on\_death\_gfx\_leave\_sprite**: `0` - Does not leave a sprite upon death.
*   **on\_lifetime\_out\_explode**: `0` - Does not explode when lifetime expires.
*   **explosion\_dont\_damage\_shooter**: `0` - The explosion can damage the shooter.
*   **die\_on\_low\_velocity**: `0` - Does not die when velocity is low.
*   **damage**: `0` - Deals no direct damage.
*   **on\_collision\_die**: `0` - Does not die on collision.
*   **lifetime**: `19` - The projectile exists for 19 frames.
*   **config\_explosion**: Empty, indicating no specific explosion configuration.

### Variable Storage Component (`VariableStorageComponent`)

*   **name**: `entity_list`
*   **value\_string**: `worms` - Likely used to identify or spawn "worms" upon certain events.

### Lua Component (`LuaComponent`)

This component integrates custom Lua scripting for advanced behavior.

*   **execute\_every\_n\_frame**: `-1` - Script does not execute periodically.
*   **execute\_on\_removed**: `1` - Script executes when the entity is removed.
*   **script\_source\_file**: `data/scripts/items/egg_hatch.lua` - The script responsible for the projectile's unique behavior, likely related to hatching or spawning.

### Audio Component (`AudioComponent`)

*   **file**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank to use.
*   **event\_root**: `player_projectiles/throwable` - Defines the root event for player-thrown projectiles.