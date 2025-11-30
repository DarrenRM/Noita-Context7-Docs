---
title: Water Essence Entity
category: entities
---

# Water Essence Entity

This entity defines the behavior and properties of the "Water Essence" in Noita, primarily managed through its associated Lua script.

## Key Components

### LuaComponent
This is the core component responsible for the essence's functionality.

*   **`_enabled`**: Set to `1`, indicating the component is active.
*   **`execute_every_n_frame`**: Set to `100`. This means the associated Lua script will execute its logic every 100 frames.
*   **`script_source_file`**: Points to `data/scripts/essences/water.lua`. This file contains the actual game logic for the Water Essence.

## Inheritance

*   **`InheritTransformComponent`**: This component suggests that the Water Essence inherits transformational properties (like position, rotation, scale) from its parent or a base entity definition.

## Tags

*   **`essence`**: Identifies this entity as a type of essence.
*   **`essence_effect`**: Indicates that this essence provides a specific effect when interacted with or applied.

## Associated Script

The primary logic for the Water Essence resides in `data/scripts/essences/water.lua`. This script would typically handle:

*   What happens when the essence is collected.
*   Any visual or auditory effects associated with the essence.
*   How the essence interacts with the game world or the player.