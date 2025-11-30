---
title: Chaotic Arc Projectile
category: entities
---

# Chaotic Arc Projectile

This entity defines a projectile with chaotic behavior, controlled by a Lua script.

## Key Components

### LuaComponent
This component is responsible for the projectile's dynamic behavior.

*   **`script_source_file`**: `data/scripts/projectiles/chaotic_arc.lua` - Specifies the Lua script that governs the projectile's logic.
*   **`execute_every_n_frame`**: `2` - The script will be executed every 2 frames, allowing for frequent updates to the projectile's trajectory and effects.

```xml
<Entity>
    <LuaComponent
        script_source_file="data/scripts/projectiles/chaotic_arc.lua"
        execute_every_n_frame="2">
    </LuaComponent>
</Entity>
```