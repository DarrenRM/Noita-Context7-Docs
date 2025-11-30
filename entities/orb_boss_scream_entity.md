---
title: Orb Boss Scream Entity
category: entities
---

# Orb Boss Scream Entity

This entity defines the behavior and appearance of the "Orb Boss Scream" in Noita. It primarily relies on a Lua script to manage its functionality.

## Core Components

### LuaComponent

This is the primary component responsible for the entity's logic.

*   **`script_source_file`**: `data/scripts/items/orb_boss_scream.lua` - Specifies the Lua script that controls the entity's behavior.
*   **`execute_every_n_frame`**: `1260` - Indicates that the Lua script will be executed every 1260 frames, defining the timing of its actions.

### InheritTransformComponent

This component suggests that the entity inherits transformation properties (like position, rotation, scale) from its parent or a base entity. This is a common component for entities that don't have unique transformational needs defined directly.