---
title: Boss Pit Spawner Entity
category: entities
---

# Boss Pit Spawner Entity

This entity acts as a conditional spawner for the "Boss Pit" enemy in Noita. It has a low chance of spawning the boss and then immediately self-destructs.

## Key Attributes

*   **Conditional Spawning:** The `boss_pit.xml` entity is only loaded if a random check (1 in 10 chance) succeeds.
*   **Random Seed:** Uses the entity's transform (x, y) to set a random seed, ensuring varied outcomes across different spawns.
*   **Self-Destruction:** After its spawning logic, the spawner entity is immediately killed using `EntityKill`.

## Lua Script Breakdown

The core logic is handled by a simple Lua script:

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

SetRandomSeed( x, y )

-- 5% chance to spawn the boss
if ( Random( 1, 10 ) == 5 ) then
	EntityLoad( "data/entities/animals/boss_pit/boss_pit.xml", x, y )
end

-- The spawner entity is removed after its logic
EntityKill( entity_id )
```