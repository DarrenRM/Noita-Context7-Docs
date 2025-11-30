---
title: Music Machine Reset Entity
category: entities
---

---

# Music Machine Reset Entity

This entity is designed to reset certain effects and tags associated with music machines. It's typically used to clean up lingering states when the game might have been closed unexpectedly.

## Key Functionality

*   **FX Reset:** Disables any active visual effects (`fx`) associated with the entity.
*   **Fish Attractor Removal:** Removes the `fish_attractor` tag, preventing unintended behavior related to fish.

## Lua Script Breakdown

The core logic is handled by a simple Lua script.

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

-- ensure fx are not left running in case game was closed while the machine was active
local entity = GetUpdatedEntityID()
EntitySetComponentsWithTagEnabled( entity, "fx", false )
EntityRemoveTag( entity, "fish_attractor" )
```

### Important Functions Used

*   `GetUpdatedEntityID()`: Retrieves the unique identifier for the entity being updated.
*   `EntitySetComponentsWithTagEnabled( entity, tag, enabled )`: Enables or disables components of an entity that have a specific tag. In this case, it disables `fx` components.
*   `EntityRemoveTag( entity, tag )`: Removes a specified tag from an entity. Here, it removes the `fish_attractor` tag.