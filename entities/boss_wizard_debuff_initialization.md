---
title: Boss Wizard Debuff Initialization
category: entities
---

---

# Boss Wizard Debuff Initialization

This script is responsible for spawning a debuff entity associated with the boss wizard. It checks if the player is present and, if so, loads and attaches the debuff entity to the player. The script then self-destructs.

## Core Functionality

*   **Player Check:** Verifies the existence of the player unit.
*   **Debuff Spawning:** Loads the `debuff.xml` entity.
*   **Parenting:** Attaches the spawned debuff entity as a child to the player.
*   **Self-Destruction:** Removes the initialization entity after its task is complete.

## Key Elements

### Player Detection

```lua
local p = EntityGetWithTag( "player_unit" )

if ( #p > 0 ) then
	local pl = p[1]
	-- ... spawn debuff ...
end
```

This snippet retrieves all entities tagged as `"player_unit"`. If at least one player entity is found, the script proceeds to spawn the debuff.

### Debuff Entity Loading and Attachment

```lua
local eid = EntityLoad( "data/entities/animals/boss_wizard/debuff.xml" )
EntityAddChild( pl, eid )
```

*   `EntityLoad("data/entities/animals/boss_wizard/debuff.xml")`: Loads the XML definition for the debuff entity.
*   `EntityAddChild(pl, eid)`: Makes the loaded debuff entity a child of the player entity (`pl`). This typically means the debuff will follow the player or be applied directly to them.

### Entity Cleanup

```lua
EntityKill( entity_id )
```

This line ensures that the initialization script entity itself is removed from the game world once its purpose is fulfilled, preventing unnecessary entities from accumulating.