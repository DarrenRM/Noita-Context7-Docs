---
title: Greed Meteor Spell
category: scripts
---

# Greed Meteor Spell

This script defines the behavior for a spell that summons a cluster of gold nuggets around the caster.

## Core Functionality

The spell's primary function is to spawn multiple gold nugget entities in a circular pattern around the player.

### Key Attributes

*   **`how_many`**: Determines the number of gold nuggets to spawn.
*   **`circle`**: A constant representing a full circle (2 * pi).
*   **`dir`**: Calculates the angular separation between each spawned nugget.
*   **`opts`**: A table containing the names of different gold nugget item XML files to be spawned.
*   **`EntityLoad`**: The function used to instantiate the gold nugget entities at calculated positions.

## Spawn Logic

The script iterates a set number of times (`how_many`) to spawn each gold nugget.

### Nugget Placement

*   Nuggets are positioned in a circle around the caster's `x` and `y` coordinates.
*   The `math.cos` and `math.sin` functions are used to calculate the `ox` (offset x) and `oy` (offset y) for each nugget based on its angle in the circle.
*   A multiplier of `12` is applied to the trigonometric results to control the radius of the spawn circle.

### Nugget Variety

*   A random selection process (`Random(0, 2) * Random(0, 1) * Random(0, 1)`) is used to pick which type of gold nugget from the `opts` table will be spawned. This introduces a slight bias towards the earlier entries in the `opts` table.

## Dependencies

*   `dofile_once( "data/scripts/lib/utilities.lua" )`: Imports utility functions.

## Example Usage (Conceptual)

This script would be triggered when a player casts a spell associated with this Lua file. The spell's configuration in its XML would define the casting parameters and link to this script.

```lua
-- Example of how the spell might be defined in its XML (not part of this script)
-- <spell>
--   <property name="script" value="data/scripts/magic/greed_curse/greed_meteor.lua" />
--   ... other properties ...
-- </spell>
```