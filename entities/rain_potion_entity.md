---
title: Rain Potion Entity
category: entities
---

# Rain Potion Entity

This document describes the `rain_potion.xml` entity, which is designed to trigger a rain effect in Noita.

## Key Components

### Entity
The root element for the entity.

### InheritTransformComponent
This component indicates that the entity will inherit transformation properties from its parent.

### LifetimeComponent
*   **lifetime**: `300` - Defines the duration in frames for which this entity will exist.

### LuaComponent
This component enables custom Lua scripting for the entity.
*   **_enabled**: `1` - Ensures the Lua script is active.
*   **execute_every_n_frame**: `20` - The script will execute every 20 frames.
*   **script_source_file**: `data/scripts/streaming_integration/scripts/rain_potion.lua` - Specifies the Lua script file responsible for the entity's behavior. This script likely handles the logic for initiating the rain effect.