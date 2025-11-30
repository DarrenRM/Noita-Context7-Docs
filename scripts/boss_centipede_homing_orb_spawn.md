---
title: Boss Centipede Homing Orb Spawn
category: guides
---

--[[
This file defines the behavior for a projectile spawned by the boss centipede.
It's a simple projectile that creates a muzzle flash effect upon spawning.
]]--

dofile( "data/scripts/lib/utilities.lua" )

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Spawn a blue circular muzzle flash at the entity's position
EntityLoad( "data/entities/particles/muzzle_flashes/muzzle_flash_circular_blue.xml", pos_x, pos_y)
```

---
title: Boss Centipede Homing Orb Spawn
category: entities
---

# Boss Centipede Homing Orb Spawn

This entity defines the behavior for a projectile spawned by the boss centipede. Its primary function is to create a visual effect upon its creation.

## Key Attributes

*   **`entity_id`**: A unique identifier for the spawned entity.
*   **`pos_x`, `pos_y`**: The X and Y coordinates where the entity is spawned.

## Behavior

*   **Visual Effect**: Upon spawning, this entity loads and displays a blue circular muzzle flash particle effect at its location.

### Lua Script Breakdown

The script is straightforward:

1.  **`dofile( "data/scripts/lib/utilities.lua" )`**: Includes utility functions from the game's script library.
2.  **`local entity_id = GetUpdatedEntityID()`**: Retrieves the unique ID of the current entity being processed.
3.  **`local pos_x, pos_y = EntityGetTransform( entity_id )`**: Gets the current position (X and Y coordinates) of the entity.
4.  **`EntityLoad( "data/entities/particles/muzzle_flashes/muzzle_flash_circular_blue.xml", pos_x, pos_y)`**: This is the core action. It loads an entity from a specified XML file (a blue muzzle flash particle effect) and places it at the `pos_x`, `pos_y` coordinates.

This entity acts as a simple visual cue for the boss's attack, rather than having complex projectile mechanics itself.