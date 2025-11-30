---
title: Boss Wizard Spawner
category: entities
---

---

# Boss Wizard Spawner

This script is responsible for spawning a random boss wizard entity.

## Functionality

The script selects a random boss wizard variant from a predefined list and loads it at the spawner's location. The spawner entity itself is then immediately killed.

## Key Attributes

*   **`opts`**: A Lua table containing the names of the different boss wizard entity files to choose from. These include variations like:
    *   `wizard_tele`
    *   `wizard_dark`
    *   `wizard_poly`
    *   `wizard_homing`
    *   `wizard_weaken`
    *   `wizard_twitchy`
    *   `wizard_neutral`
    *   `wizard_hearty`
    *   `wizard_returner`

## Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

SetRandomSeed( x, y * entity_id )

local opts = { "wizard_tele", "wizard_dark", "wizard_poly", "wizard_homing", "wizard_weaken", "wizard_twitchy", "wizard_neutral", "wizard_hearty", "wizard_returner" }

for i=1,1 do
	local rnd = Random( 1, #opts )
	EntityLoad( "data/entities/animals/" .. opts[rnd] .. ".xml", x, y )
end

EntityKill( entity_id )
```