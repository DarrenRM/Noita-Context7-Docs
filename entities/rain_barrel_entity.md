---
title: Rain Barrel Entity
category: entities
---

---

# Rain Barrel Entity

This document describes the `rain_barrel.xml` entity, which represents a rain barrel in Noita.

## Entity Definition

The `rain_barrel.xml` entity is a basic entity with the following key components:

### Core Components

*   **`LifetimeComponent`**:
    *   `lifetime`: Specifies the duration (in frames) for which the entity will exist. In this case, it's set to `160` frames.

*   **`LuaComponent`**:
    *   `_enabled`: Controls whether the Lua script is active. Set to `1` (enabled).
    *   `execute_every_n_frame`: Determines how often the associated Lua script will execute. Set to `20` frames.
    *   `script_source_file`: Points to the Lua script that controls the entity's behavior. Here, it's `data/scripts/streaming_integration/scripts/rain_barrel.lua`.

This entity is designed to interact with the game's streaming integration, likely for managing rain-related mechanics or visual effects. The `LuaComponent` is the primary driver of its functionality, executing a specific script at regular intervals.