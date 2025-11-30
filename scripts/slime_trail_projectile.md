---
title: Slime Trail Projectile
category: scripts
---

# Slime Trail Projectile

This script defines the behavior for a projectile that spawns other projectiles, specifically slime blobs.

## Core Functionality

The primary purpose of this script is to act as a "spawner" for other projectiles. When this projectile is active, it generates a `slimeblob.xml` projectile.

## Key Attributes

*   **`shoot_projectile_from_projectile`**: This is the core function used. It takes the current projectile's entity ID and spawns a new projectile based on a specified XML file.
*   **`entity_id`**: The unique identifier for the current projectile entity.
*   **`pos_x`, `pos_y`**: The current position of the projectile.
*   **`vel_x`, `vel_y`**: The velocity components of the projectile.

## Spawning Logic

1.  **Initialization**: The script retrieves the current projectile's entity ID and its position.
2.  **Randomization**: A random seed is generated based on game frame number and projectile position for deterministic randomness.
3.  **Position Offset**: The spawn position for the new projectile is slightly randomized around the current projectile's position.
4.  **Velocity Generation**: Random velocity is generated for the new projectile.
5.  **Projectile Creation**: The `shoot_projectile_from_projectile` function is called to create a `slimeblob.xml` projectile at the calculated position and with the generated velocity.

## Example Usage (Conceptual)

This script would typically be attached to a projectile entity that is intended to leave a trail of slime blobs. For instance, a projectile that, upon impact or over time, continuously spawns smaller slime projectiles.

```lua
-- Example of how this script might be referenced in an entity XML
-- (This is illustrative and not directly from the provided Lua)

-- <Entity name="slime_trail_emitter">
--     <LuaComponent script_path="data/scripts/projectiles/slimetrail.lua" />
--     ... other components ...
-- </Entity>
```