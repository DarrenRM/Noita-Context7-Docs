---
title: Disable Homing on Polyp Boss Ghost
category: entities
---

# Disable Homing on Polyp Boss Ghost

This script disables the homing behavior for entities tagged with "polyp_homing". It's a simple utility to modify the behavior of specific entities, likely related to the Polyp boss in Noita.

## Key Functionality

*   **Disables Homing:** The primary function is to turn off the homing capabilities of targeted entities.

## Lua Script

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id = GetUpdatedEntityID()

EntitySetComponentsWithTagEnabled( entity_id, "polyp_homing", false )
```

## Explanation

1.  `dofile_once( "data/scripts/lib/utilities.lua" )`: This line ensures that the `utilities.lua` script is loaded only once, preventing potential conflicts or redundant loading of common functions.
2.  `local entity_id = GetUpdatedEntityID()`: This retrieves the unique identifier for the current entity being processed by the script.
3.  `EntitySetComponentsWithTagEnabled( entity_id, "polyp_homing", false )`: This is the core function call.
    *   `entity_id`: Specifies the entity to modify.
    *   `"polyp_homing"`: This is the tag that identifies the components responsible for the homing behavior.
    *   `false`: This argument disables the components associated with the `"polyp_homing"` tag.

## Usage in Modding

This script is useful for:

*   Creating variations of the Polyp boss with different attack patterns.
*   Disabling homing on specific projectiles or enemies for balance or gameplay changes.
*   Debugging or testing the behavior of homing mechanics.