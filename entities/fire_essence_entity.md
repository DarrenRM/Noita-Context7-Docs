---
title: Fire Essence Entity
category: entities
---

# Fire Essence Entity

This entity defines the behavior and properties of the Fire Essence in Noita.

## Core Components

### LuaComponent
This component is responsible for the essence's dynamic behavior, executing a Lua script at regular intervals.

*   **`script_source_file`**: `data/scripts/essences/fire.lua` - Specifies the Lua script that controls the essence's logic.
*   **`execute_every_n_frame`**: `120` - The script will be executed every 120 frames.

### InheritTransformComponent
This component indicates that the entity inherits its transform properties (position, rotation, scale) from its parent or context.

## Entity Tags

*   `essence`: Identifies this entity as an essence.
*   `essence_effect`: Further categorizes it as an essence that produces an effect.