---
title: Ping Pong Path Entity
category: entities
---

# Ping Pong Path Entity

This entity defines a projectile that bounces back and forth. It's primarily controlled by a Lua script.

## LuaComponent

This component links the entity to its behavior defined in a Lua script.

### Key Attributes:

*   **`_tags`**: `pingpong_path` - Identifies this entity as a ping pong path projectile.
*   **`script_source_file`**: `data/scripts/projectiles/pingpong_path.lua` - Specifies the Lua script that governs the projectile's behavior.
*   **`execute_every_n_frame`**: `13` - The script logic will be executed every 13 frames.

## Entity

The root element for this entity.

### Key Elements:

*   **`LuaComponent`**: As described above, this is the core component that gives the entity its functionality.

---
```xml
<Entity>
    <LuaComponent
        _tags="pingpong_path"
        script_source_file="data/scripts/projectiles/pingpong_path.lua"
        execute_every_n_frame="13">
    </LuaComponent>
</Entity>
```