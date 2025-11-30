---
title: Neutralized Effect Entity
category: entities
---

# Neutralized Effect Entity

This entity defines the behavior and properties of the "neutralized" effect in Noita, typically applied to projectiles or other entities to alter their behavior.

## Core Components

### LuaComponent

This component is responsible for executing custom Lua scripting for the entity.

*   **`script_shot`**: Specifies the Lua script file to be executed. In this case, it points to `data/scripts/projectiles/neutralized.lua`, indicating that this entity is likely used to modify projectile behavior.
*   **`execute_every_n_frame`**: Set to `-1`, meaning the script is not executed on a fixed frame interval but rather triggered by events or other game logic.

### LifetimeComponent

This component manages how long the entity persists in the game world.

*   **`lifetime`**: Set to `900` frames, defining the duration of the neutralized effect.

## Inheritance

*   **`InheritTransformComponent`**: This indicates that the entity inherits transformation properties (like position, rotation, and scale) from its parent or the entity it's attached to. This is common for effects that should follow the object they are applied to.