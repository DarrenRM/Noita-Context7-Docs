---
title: Transmutation Entity
category: entities
---

# Transmutation Entity

This entity defines a transmutation effect within Noita, likely used for visual or gameplay-related transformations.

## Core Components

### InheritTransformComponent
*   **Purpose:** Inherits transformation properties from its parent entity. This is a common component for entities that need to maintain their position, rotation, and scale relative to another object.

### LuaComponent
*   **Purpose:** Executes Lua scripts to define custom behavior.
*   **Key Attributes:**
    *   `_enabled`: Controls whether the Lua component is active (1 for enabled, 0 for disabled).
    *   `execute_every_n_frame`: Determines how often the script is executed (e.g., `100` means every 100 frames).
    *   `script_source_file`: Specifies the path to the Lua script file that will be executed. In this case, it's `data/scripts/streaming_integration/scripts/transmutation.lua`.

### LifetimeComponent
*   **Purpose:** Manages the lifespan of the entity.
*   **Key Attributes:**
    *   `lifetime`: The duration in frames the entity will exist before being removed. Here, it's set to `900` frames.

## Entity Tags

*   `transmutation`: This tag likely identifies the entity as a transmutation effect, allowing other game systems to recognize and interact with it.