---
title: Gold Rain Projectile
category: entities
---

# Gold Rain Projectile

This entity defines the behavior and properties of the "Gold Rain" projectile in Noita. It's primarily used to create a visual and functional effect of gold particles falling.

## Key Components

### LifetimeComponent
Controls how long the projectile entity exists.

*   **lifetime**: `120` (seconds) - The duration the gold rain effect will persist.

### LuaComponent
Attaches a Lua script to the entity, enabling custom logic.

*   **_enabled**: `1` - Ensures the script is active.
*   **execute_every_n_frame**: `5` - The script's logic will run every 5 frames.
*   **script_source_file**: `data/scripts/projectiles/rain_gold.lua` - Specifies the Lua script responsible for the gold rain's behavior.

## Inherited Components

*   **InheritTransformComponent**: This component is present but has no configurable attributes in this definition. It likely handles the entity's position and transformation within the game world.