---
title: Eradicate Entity
category: entities
---

# Eradicate Entity

This entity is responsible for the "Eradicate" magic spell in Noita. It utilizes a Lua script to perform its function and has a defined lifetime.

## Key Components

### LuaComponent
This component links the entity to its behavior defined in a Lua script.

*   **`script_source_file`**: `data/scripts/magic/eradicate.lua` - Specifies the script file that controls the entity's logic.
*   **`execute_every_n_frame`**: `100` - The script will execute its logic every 100 frames.

### LifetimeComponent
This component defines how long the entity will exist.

*   **`lifetime`**: `6000` - The entity will persist for 6000 frames.

### InheritTransformComponent
This component indicates that the entity inherits transformation properties (like position, rotation, scale) from its parent or the context it's spawned in.