---
title: Waterstone Stain Effect
category: guides
---

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

local targets = EntityGetInRadiusWithTag( x, y, 64, "hittable" )

for i,eid in pairs( targets ) do
	EntityAddRandomStains( eid, CellFactory_GetType("water"), 400 )
end
```

---
title: Waterstone Stain Effect
category: scripts
---

# Waterstone Stain Effect

This script defines the behavior of the "Waterstone" item in Noita, specifically its ability to apply water stains to nearby "hittable" entities.

## Key Functionality

*   **Entity Identification:** The script first retrieves the unique ID of the entity it's attached to and its world coordinates (`x`, `y`).
*   **Target Detection:** It then searches for entities within a 64-unit radius that possess the "hittable" tag.
*   **Stain Application:** For each detected "hittable" entity, the script applies a water stain.
    *   The stain type is "water" (obtained via `CellFactory_GetType("water")`).
    *   The stain intensity or amount is set to 400.

## Script Breakdown

```lua
local entity_id = GetUpdatedEntityID() -- Gets the unique identifier for the current entity.
local x, y = EntityGetTransform( entity_id ) -- Retrieves the world coordinates (x, y) of the entity.

-- Finds all entities within a 64-unit radius that have the "hittable" tag.
local targets = EntityGetInRadiusWithTag( x, y, 64, "hittable" )

-- Iterates through each found target entity.
for i,eid in pairs( targets ) do
	-- Adds a random water stain to the target entity.
	-- CellFactory_GetType("water") specifies the type of stain.
	-- 400 is the intensity/amount of the stain.
	EntityAddRandomStains( eid, CellFactory_GetType("water"), 400 )
end