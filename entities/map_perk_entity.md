---
title: Map Perk Entity
category: entities
---

# Map Perk Entity

This entity defines the behavior and properties of the "Map" perk in Noita.

## Core Components

### LuaComponent

This component links the entity to its associated Lua script, which handles the perk's logic.

*   **`script_source_file`**: `data/scripts/perks/map.lua` - Specifies the path to the Lua script responsible for the perk's functionality.
*   **`execute_every_n_frame`**: `1` - Indicates that the script should be executed every frame, allowing for real-time updates and checks.

### VariableStorageComponent

This component stores persistent variables associated with the entity.

*   **`name`**: `map_timer` - The name of the variable.
*   **`value_int`**: `0` - The initial integer value of the `map_timer`. This likely tracks time or a countdown related to the perk.

## Inheritance

### InheritTransformComponent

This component indicates that the entity inherits transform properties (position, rotation, scale) from its parent or a base entity. In this case, it's likely a placeholder or a standard component for entities.