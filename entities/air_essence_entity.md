---
title: Air Essence Entity
category: entities
---

# Air Essence Entity

This entity defines the behavior and properties of the "Air Essence" in Noita. It's primarily used to create environmental effects related to air.

## Key Components

### LuaComponent

This component is responsible for executing the custom Lua script that defines the essence's behavior.

*   **`_enabled`**: `1` (Indicates the component is active).
*   **`execute_every_n_frame`**: `40` (The script will execute approximately every 40 frames).
*   **`script_source_file`**: `data/scripts/essences/air.lua` (Specifies the Lua script file that controls the essence's logic).

### InheritTransformComponent

This component indicates that the entity inherits its transformation properties (position, rotation, scale) from its parent or context.

## Tags

*   `essence`
*   `essence_effect`

These tags categorize the entity as a type of essence and mark it as having an effect.