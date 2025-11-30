---
title: Statue Trap Right Entity
category: entities
---

# Statue Trap Right Entity

This document describes the `statue_trap_right.xml` entity, which represents a right-facing statue trap in Noita.

## Entity Definition

The core entity definition for the statue trap.

```xml
<Entity 
  name="unknown" 
  tags="" >
  </Entity>
```

## Key Components

### SpriteComponent

Handles the visual representation of the statue trap.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/buildings_gfx/statue_trap_right.xml" 
  offset_x="0" 
  offset_y="0" 
>
</SpriteComponent>
```

*   **`image_file`**: Specifies the graphical asset used for the sprite.

### SimplePhysicsComponent

Indicates that this entity has basic physics properties.

```xml
<SimplePhysicsComponent />
```

### VelocityComponent

Indicates that this entity can have velocity.

```xml
<VelocityComponent />
```

### LuaComponent

Attaches a Lua script to the entity, defining its behavior.

```xml
<LuaComponent
  script_source_file="data/scripts/buildings/statue_trap.lua"
  execute_every_n_frame="40"
>
</LuaComponent>
```

*   **`script_source_file`**: The path to the Lua script that controls the entity's logic.
*   **`execute_every_n_frame`**: Determines how frequently the Lua script's logic is executed. In this case, it runs every 40 frames.