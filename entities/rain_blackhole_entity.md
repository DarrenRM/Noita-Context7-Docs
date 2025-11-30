---
title: Rain Blackhole Entity
category: entities
---

# Rain Blackhole Entity

This entity represents a blackhole that appears during rain events. It is primarily controlled by a Lua script.

## Key Components

### InheritTransformComponent
This component indicates that the entity inherits its transformation properties (position, rotation, scale) from its parent.

### LifetimeComponent
*   **lifetime**: `240` - The entity will exist for 240 frames.

### LuaComponent
*   **_enabled**: `1` - The Lua script is enabled.
*   **execute_every_n_frame**: `60` - The associated Lua script will execute every 60 frames.
*   **script_source_file**: `data/scripts/streaming_integration/scripts/rain_blackhole.lua` - This specifies the Lua script that governs the entity's behavior. This script is responsible for the actual blackhole mechanics, such as its visual effects, gravitational pull, and interaction with the environment.