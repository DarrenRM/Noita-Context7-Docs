---
title: Rain Hiisi Entity
category: entities
---

# Rain Hiisi Entity

This document describes the `rain_hiisi.xml` entity, which is designed to integrate with Noita's streaming system to spawn Hiisi entities during rain.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

### Key Components

*   **`<InheritTransformComponent />`**: This component indicates that the entity will inherit transformation properties, likely from its parent or spawning context.
*   **`<LifetimeComponent lifetime="200" />`**: This component defines the lifespan of the entity. In this case, it will exist for 200 frames.
*   **`<LuaComponent _enabled="1" execute_every_n_frame="20" script_source_file="data/scripts/streaming_integration/scripts/rain_hiisi.lua" />`**: This is the primary component responsible for the entity's behavior.
    *   `_enabled="1"`: Ensures the Lua script is active.
    *   `execute_every_n_frame="20"`: The associated Lua script will execute its logic every 20 frames.
    *   `script_source_file="data/scripts/streaming_integration/scripts/rain_hiisi.lua"`: This specifies the path to the Lua script that controls the entity's functionality. This script is responsible for the actual spawning of Hiisi entities when rain conditions are met.

## Associated Lua Script

The behavior of the `rain_hiisi` entity is governed by the `data/scripts/streaming_integration/scripts/rain_hiisi.lua` file. This script would typically contain logic to:

*   Detect rain events.
*   Determine spawn locations and conditions for Hiisi.
*   Instantiate Hiisi entities using Noita's entity spawning functions.
*   Potentially manage the rate and density of Hiisi spawns.