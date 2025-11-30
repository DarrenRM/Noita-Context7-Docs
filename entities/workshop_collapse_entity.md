---
title: Workshop Collapse Entity
category: entities
---

# Workshop Collapse Entity

This entity defines a special "workshop collapse" effect in Noita, primarily used for transforming specific materials over time.

## Core Components

### LuaComponent
This component links the entity to its behavior defined in a Lua script.

*   **script_source_file**: `data/scripts/buildings/workshop_collapse.lua` - The primary script governing the entity's actions.
*   **vm_type**: `ONE_PER_COMPONENT_INSTANCE` - Indicates the Lua virtual machine setup.
*   **enable_coroutines**: `1` - Allows for asynchronous execution within the script.
*   **execute_on_added**: `1` - The script will execute immediately when the entity is added to the game.
*   **execute_times**: `1` - The script will execute only once.

### LifetimeComponent
This component controls how long the entity persists in the game world.

*   **lifetime**: `320` - The base duration in frames the entity will exist.
*   **randomize_lifetime.min**: `-50` - Minimum random variation added to the lifetime.
*   **randomize_lifetime.max**: `50` - Maximum random variation added to the lifetime.

### MagicConvertMaterialComponent
This is the core component responsible for the material transformation effect.

*   **from_material**: `glowstone_altar` - The material that will be transformed.
*   **to_material**: `templebrick_noedge_static` - The material that the `from_material` will be converted into.
*   **radius**: `128` - The area of effect for the material conversion.
*   **steps_per_frame**: `1` - Controls the speed of the conversion process.
*   **kill_when_finished**: `0` - The entity will not be destroyed automatically after the conversion is complete.