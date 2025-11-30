---
title: Racing Stopwatch Entity
category: entities
---

# Racing Stopwatch Entity

This document describes the `racing_stopwatch.xml` entity, which functions as a stopwatch for racing mechanics in Noita.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

### Key Attributes

*   **`tags`**: `racing_stopwatch` - Identifies this entity as a racing stopwatch.

## Components

### VariableStorageComponent

This component stores a variable named `time`.

*   **`name`**: `time` - The name of the variable.
*   **`value_int`**: `0` - The initial integer value of the stopwatch, starting at zero.

### LuaComponent

This component enables custom Lua scripting for the stopwatch's behavior.

*   **`script_source_file`**: `data/scripts/buildings/racing_stopwatch.lua` - Specifies the Lua script file that controls the stopwatch's logic.
*   **`execute_every_n_frame`**: `1` - The script will execute every single frame, allowing for precise timing.