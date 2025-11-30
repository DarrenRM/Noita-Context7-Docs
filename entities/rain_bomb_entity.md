---
title: Rain Bomb Entity
category: entities
---

---

# Rain Bomb Entity

This document describes the `rain_bomb.xml` entity, which is designed to trigger a rain effect in Noita.

## Core Components

The `rain_bomb.xml` entity primarily utilizes the following components:

### InheritTransformComponent

*   **Purpose:** This component indicates that the entity inherits its transformation properties (position, rotation, scale) from its parent. This is a common component for entities that are spawned or placed within the game world.

### LifetimeComponent

*   **Purpose:** Manages the lifespan of the entity.
*   **Key Attribute:**
    *   `lifetime`: The duration in frames the entity will exist before being removed. In this case, it's set to `80` frames.

### LuaComponent

*   **Purpose:** Enables custom Lua scripting for the entity. This is where the logic for triggering the rain effect resides.
*   **Key Attributes:**
    *   `_enabled`: A flag to enable or disable the Lua component. Set to `1` (enabled).
    *   `execute_every_n_frame`: Determines how often the Lua script's `on_frame` function is called. Set to `10` frames, meaning the script logic runs every 10 frames.
    *   `script_source_file`: Specifies the path to the Lua script file that controls the entity's behavior. Here, it points to `data/scripts/streaming_integration/scripts/rain_bomb.lua`.

## Lua Scripting

The `LuaComponent` references `data/scripts/streaming_integration/scripts/rain_bomb.lua`. This script is responsible for the actual implementation of the rain effect. While the script content is not provided in the XML, it would typically handle:

*   Detecting when the `rain_bomb` entity is active.
*   Spawning rain particles or projectiles.
*   Potentially managing the duration and intensity of the rain.
*   Interacting with other game systems to create the visual and auditory experience of rain.