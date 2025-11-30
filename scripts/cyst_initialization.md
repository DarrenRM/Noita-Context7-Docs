---
title: Cyst Initialization
category: scripts
---

# Cyst Initialization

This script handles the initial setup and transformation of a "cyst" entity in Noita.

## Key Functionality

The primary purpose of this script is to:

1.  **Get Entity ID:** Retrieve the unique identifier for the entity being processed.
2.  **Get Position:** Obtain the current X and Y coordinates of the entity.
3.  **Set Random Rotation:** Apply a random rotation to the entity based on its position, ensuring variety in its placement.

## Core Logic

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity_id )

local angle = ProceduralRandom(x, y) * 3.1415926535 * 2
EntitySetTransform( entity_id, x, y, angle )
```

### Explanation of Key Functions:

*   `GetUpdatedEntityID()`: Returns the ID of the entity that this script is attached to.
*   `EntityGetTransform( entity_id )`: Retrieves the position (x, y) and rotation of the specified entity.
*   `ProceduralRandom(x, y)`: Generates a pseudo-random number based on the entity's coordinates. This ensures that each cyst will have a unique random value.
*   `EntitySetTransform( entity_id, x, y, angle )`: Sets the position and rotation of the specified entity. In this case, it updates the entity's rotation while keeping its position the same.