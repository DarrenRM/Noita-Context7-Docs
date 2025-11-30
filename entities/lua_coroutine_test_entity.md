---
title: Lua Coroutine Test Entity
category: entities
---

# Lua Coroutine Test Entity

This entity demonstrates the use of Lua coroutines within Noita's entity system. It's primarily for testing and debugging coroutine functionality.

## LuaComponent

This component enables the execution of Lua scripts.

### Key Attributes:

*   **`script_source_file`**: Specifies the path to the Lua script to be executed. In this case, it's `data/scripts/buildings/altar_collapse.lua`.
*   **`vm_type`**: Determines how the Lua virtual machine is managed. `ONE_PER_COMPONENT_INSTANCE` means each `LuaComponent` gets its own VM.
*   **`enable_coroutines`**: Set to `1` to enable coroutine support for this component.
*   **`execute_on_added`**: Set to `1`, meaning the script will execute immediately when the entity is added to the game world.
*   **`execute_every_n_frame`**: Set to `-1`, indicating the script does not execute on a frame-by-frame basis.
*   **`execute_times`**: Set to `1`, meaning the script will execute only once.

```xml
<Entity>
    <LuaComponent
        script_source_file="data/scripts/buildings/altar_collapse.lua"
        vm_type="ONE_PER_COMPONENT_INSTANCE"
        enable_coroutines="1"
        execute_on_added="1"
        execute_every_n_frame="-1"
        execute_times="1">
    </LuaComponent>
</Entity>
```