---
title: Greed Rain Simple Entity
category: entities
---

# Greed Rain Simple Entity

This entity defines a simple "greed rain" effect, likely used for a curse or special event in Noita. It spawns meteors periodically.

## Key Components

### InheritTransformComponent
*   This component indicates that the entity inherits its transform properties (position, rotation, scale) from its parent.

### LifetimeComponent
*   **lifetime**: `300` - The total duration this entity will exist in frames.
*   **serialize_duration**: `1` - How long the entity's duration should be serialized.

### LuaComponent
*   **_enabled**: `1` - This component is active.
*   **execute_every_n_frame**: `10` - The associated Lua script will execute every 10 frames.
*   **script_source_file**: `data/scripts/magic/greed_curse/spawn_meteors_simple.lua` - This points to the Lua script responsible for the entity's behavior, specifically spawning meteors.