---
title: Temporary Workshop Entity
category: entities
---

# Temporary Workshop Entity

This entity represents a temporary workshop that can be placed in the game world. It's primarily used for scripting and interaction rather than being a permanent structure.

## Key Components

### HitboxComponent
Defines the physical boundaries of the workshop entity.

*   `aabb_min_x`: Minimum X-axis coordinate of the bounding box.
*   `aabb_min_y`: Minimum Y-axis coordinate of the bounding box.
*   `aabb_max_x`: Maximum X-axis coordinate of the bounding box.
*   `aabb_max_y`: Maximum Y-axis coordinate of the bounding box.

```xml
<HitboxComponent
    aabb_min_x="-200"
    aabb_min_y="-96"
    aabb_max_x="200"
    aabb_max_y="80" >
</HitboxComponent>
```

### LuaComponent
Attaches a Lua script to the entity, enabling custom behavior.

*   `script_source_file`: Path to the Lua script file that controls the entity's logic.
*   `execute_every_n_frame`: Specifies how often the script's `update` function should be called (in frames).

```xml
<LuaComponent
    script_source_file="data/scripts/buildings/workshop_temporary_check.lua"
    execute_every_n_frame="20"
    >
</LuaComponent>
```

## Entity Tags

*   `workshop`: Indicates that this entity is a type of workshop.

```xml
<Entity tags="workshop">
    ...
</Entity>
```