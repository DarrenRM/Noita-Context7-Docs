---
title: Plague Rats Rat Poof Perk Effect
category: scripts/perks
---

# Plague Rats Rat Poof Perk Effect

This script defines the visual and functional effect of the "Plague Rats" perk when it triggers a rat poof.

## Core Functionality

When this perk is active and a rat poof event occurs, this script is executed. Its primary purpose is to spawn a visual effect and then remove the entity that triggered the poof.

### Key Actions

*   **Entity Identification:** Retrieves the ID and position of the entity that triggered the poof.
*   **Visual Effect Spawning:** Loads and places a specific entity (`data/entities/misc/perks/plague_rats_rat_poof.xml`) at the poof's location. This entity is responsible for the visual particles and animations associated with the rat poof.
*   **Entity Removal:** Immediately kills the original entity that triggered the poof, effectively making it disappear in a puff of rats.

## Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- do some kind of an effect? throw some particles into the air?
EntityLoad( "data/entities/misc/perks/plague_rats_rat_poof.xml", pos_x, pos_y )
EntityKill( entity_id )
```

### Important Elements

*   `dofile_once("data/scripts/lib/utilities.lua")`: Imports utility functions, likely for common game operations.
*   `GetUpdatedEntityID()`: Gets the unique identifier for the entity that is currently being processed.
*   `EntityGetTransform( entity_id )`: Retrieves the X and Y coordinates of the specified entity.
*   `EntityLoad( "data/entities/misc/perks/plague_rats_rat_poof.xml", pos_x, pos_y )`: This is the crucial line that spawns the visual effect. It loads an XML entity file located at `data/entities/misc/perks/plague_rats_rat_poof.xml` at the calculated position. This XML file would contain the particle effects, animations, and potentially any other visual components of the rat poof.
*   `EntityKill( entity_id )`: Terminates the existence of the original entity that triggered this script.