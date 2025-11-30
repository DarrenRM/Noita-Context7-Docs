---
title: Bunker 2 Check Entity
category: entities
---

# Bunker 2 Check Entity

This entity is a component used in the Noita game's modding data, specifically within the `data/entities/buildings/` directory. It serves as a trigger or check mechanism for the "Bunker 2" building.

## Key Components

### LuaComponent

This is the primary component attached to the `bunker2.xml` entity.

*   **`script_source_file`**: Specifies the Lua script that this component will execute.
    *   Value: `data/scripts/buildings/bunker2_check.lua`
*   **`execute_every_n_frame`**: Determines how frequently the attached Lua script will be executed.
    *   Value: `20` (The script will run every 20 frames).

## Purpose

The `bunker2.xml` entity, by utilizing the `LuaComponent` with the `bunker2_check.lua` script, likely plays a role in checking conditions or triggering events related to the "Bunker 2" structure within the game. The `execute_every_n_frame="20"` suggests a periodic check or update mechanism.

## Usage in Modding

Modders can leverage this structure to:

*   Understand how specific building mechanics are implemented.
*   Modify the `bunker2_check.lua` script to alter the behavior of Bunker 2.
*   Integrate similar checking mechanisms into their own custom entities.