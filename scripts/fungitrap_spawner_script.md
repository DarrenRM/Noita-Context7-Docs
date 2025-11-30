---
title: Fungitrap Spawner Script
category: scripts
---

---

# Fungitrap Spawner Script

This script controls the spawning behavior of fungitraps. It ensures that a limited number of fungitraps are active within a certain radius.

## Core Functionality

The primary purpose of this script is to act as a spawner for `physics_fungus_trap.xml` entities. It checks the current number of fungitraps in its vicinity and spawns a new one if the count is below a threshold.

## Key Attributes

*   **`entities`**: A table containing the IDs of entities with the tag "fungitrap_02" found within a radius.
*   **Radius Check**: The script checks for fungitraps within a radius of **200** units from its own position.
*   **Spawn Threshold**: A new fungitrap is spawned only if the number of existing fungitraps (`#entities`) is **less than 6**.
*   **Entity Spawning**: If the threshold is met, `data/entities/props/physics_fungus_trap.xml` is loaded at the spawner's current position.
*   **Self-Destruction**: After successfully spawning a new fungitrap, the spawner entity itself is killed (`EntityKill(entity_id)`).

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity_id )

local entities = EntityGetInRadiusWithTag( x, y, 200, "fungitrap_02" )

if ( #entities < 6 ) then
	EntityLoad( "data/entities/props/physics_fungus_trap.xml", x, y )
	EntityKill( entity_id )
end
```