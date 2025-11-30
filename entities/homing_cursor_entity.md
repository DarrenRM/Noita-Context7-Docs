---
title: Homing Cursor Entity
category: entities
---

# Homing Cursor Entity

This entity defines the behavior of a homing cursor, typically used for targeting or guiding projectiles.

## Core Components

### LuaComponent
This component is responsible for the entity's dynamic behavior, driven by a Lua script.

*   **script_source_file**: `data/scripts/projectiles/homing_cursor.lua` - Specifies the Lua script that controls the homing cursor's logic.
*   **execute_every_n_frame**: `1` - Indicates that the script should be executed every single frame, allowing for real-time updates and responsiveness.

---