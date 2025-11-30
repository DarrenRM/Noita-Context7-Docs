---
title: Bounce Larpa Projectile
category: entities
---

# Bounce Larpa Projectile

This entity defines a projectile with bouncing behavior, controlled by a Lua script.

## Key Components

### LuaComponent
This component attaches a Lua script to the entity, defining its behavior.

*   **`script_source_file`**: `data/scripts/projectiles/bounce_larpa.lua` - Specifies the Lua script that governs the projectile's logic.
*   **`execute_every_n_frame`**: `1` - The script will execute every frame.
*   **`remove_after_executed`**: `1` - The entity will be removed after the script has executed once.

```xml
<Entity>
    <LuaComponent
        script_source_file="data/scripts/projectiles/bounce_larpa.lua"
        execute_every_n_frame="1"
        remove_after_executed="1"
    />
</Entity>
```