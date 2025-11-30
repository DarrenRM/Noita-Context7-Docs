---
title: Debug Perk Entity
category: entities
---

# Debug Perk Entity

This entity defines a basic perk that can be spawned for debugging purposes. It utilizes a Lua script to handle its functionality.

## Key Components

### LuaComponent
This component is responsible for executing custom Lua script logic.

*   **script_source_file**: `data/scripts/perks/perk_spawn.lua` - Specifies the Lua script file to be executed.
*   **execute_every_n_frame**: `1` - Indicates that the script should execute every frame, allowing for real-time updates or checks.

## Entity Tags

*   `teleportable_NOT`: This tag prevents the entity from being teleported.
*   `perk`: This tag identifies the entity as a perk.

---