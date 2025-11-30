---
title: Radioactive Curse Status Effect
category: scripts
---

---

# Radioactive Curse Status Effect

This script defines the behavior for the "Radioactive Curse" status effect in Noita. When applied, it checks for specific game flags to determine if it should spawn a special entity that handles the curse's effects.

## Core Logic

The primary function of this script is to conditionally spawn an entity based on game state.

### Key Conditions:

*   **`GameHasFlagRun("greed_curse")`**: This checks if the "greed curse" is currently active in the game.
*   **`GameHasFlagRun("greed_curse_gone") == false`**: This ensures that the "greed curse" has not already been removed or resolved.

### Action on Condition Met:

If both of the above conditions are true, the script will load and place the `convert_radioactive_with_delay.xml` entity at the current position of the entity that has this status effect applied.

```lua
-- Load utility functions
dofile_once("data/scripts/lib/utilities.lua")

-- Get the ID of the entity that has this status effect
local entity_id = GetUpdatedEntityID()
-- Get the current position of the entity
local x,y = EntityGetTransform( entity_id )

-- Check if the "greed curse" is active and not yet gone
if GameHasFlagRun( "greed_curse" ) and ( GameHasFlagRun( "greed_curse_gone" ) == false ) then
	-- If conditions are met, load and spawn the radioactive conversion entity
	EntityLoad( "data/entities/misc/convert_radioactive_with_delay.xml", x,y )
end
```

## Related Entities

*   **`data/entities/misc/convert_radioactive_with_delay.xml`**: This is the entity that is spawned when the curse is active. Its XML definition would contain the actual logic for how the radioactive curse affects the game world and the player (e.g., damage over time, visual effects, etc.).