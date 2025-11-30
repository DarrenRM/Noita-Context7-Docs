---
title: Darkflame Projectile
category: scripts
---

# Darkflame Projectile

This script defines the behavior for a projectile that spawns another projectile, specifically a "darkflame_stationary" type.

## Key Functionality

*   **Spawning a Secondary Projectile:** The primary purpose of this script is to create a new projectile instance based on a predefined entity XML.
*   **Randomized Offset:** The spawned projectile is positioned with a slight random offset from the original projectile's location, adding a degree of unpredictability.

## Core Attributes

*   `entity_id`: The unique identifier for the current projectile entity.
*   `pos_x`, `pos_y`: The current X and Y coordinates of the projectile.
*   `shoot_projectile_from_projectile()`: The core function used to spawn the new projectile.

### `shoot_projectile_from_projectile()` Parameters

*   `entity_id`: The ID of the projectile initiating the spawn.
*   `"data/entities/projectiles/darkflame_stationary.xml"`: The path to the XML file defining the projectile to be spawned.
*   `pos_x`, `pos_y`: The target X and Y coordinates for the new projectile.
*   `0`, `0`: Initial velocity components (X and Y) for the spawned projectile.

## Example Usage (Conceptual)

This script would typically be attached to a projectile entity that, upon impact or after a certain duration, triggers the spawning of the `darkflame_stationary.xml` projectile.

```lua
-- Example of how this script might be triggered within a projectile's lifecycle
-- (This is illustrative and not part of the provided script)

-- Assume 'this_projectile_id' is the ID of the projectile running this script
-- and it has a component that calls this script upon some event.

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Add some randomness to the spawn location
SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )
pos_x = pos_x + Random(-8, 8)
pos_y = pos_y + Random(-8, 8)

-- Spawn the darkflame_stationary projectile
local spawned_projectile_id = shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/darkflame_stationary.xml", pos_x, pos_y, 0, 0 )

-- Further actions could be taken with 'spawned_projectile_id' if needed
```