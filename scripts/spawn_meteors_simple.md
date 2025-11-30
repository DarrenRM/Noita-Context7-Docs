---
title: Spawn Meteors Simple
category: scripts
---

---

# Spawn Meteors Simple

This script spawns a small cluster of meteors around the player's current position. It's a simple, direct implementation for triggering meteor showers.

## Key Functionality

*   **Randomized Count:** Spawns between 1 and 3 meteors per execution.
*   **Randomized Position:** Meteors are scattered horizontally around the player's X-coordinate and dropped from above the player's Y-coordinate.
*   **Randomized Velocity:** Meteors have varying horizontal and vertical velocities for a more dynamic fall.
*   **Screen Shake:** Triggers a moderate screen shake effect upon execution.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua") -- Ensures utility functions are loaded.

local entity_id    = GetUpdatedEntityID() -- Gets the ID of the entity executing this script.
local pos_x, pos_y = EntityGetTransform( entity_id ) -- Retrieves the X and Y coordinates of the entity.

-- Sets a random seed based on game frame and entity position for varied results.
SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )

local count = Random(1,3) -- Determines the number of meteors to spawn (1 to 3).

-- Loop to spawn the determined number of meteors.
for i=1,count do
	-- Shoots a projectile (meteor_green.xml) with randomized position and velocity.
	shoot_projectile(
		entity_id,
		"data/entities/projectiles/meteor_green.xml", -- The projectile entity to spawn.
		pos_x + Random( -360, 360 ), -- Randomized X position relative to the entity.
		pos_y - 300, -- Y position above the entity.
		Random( -200, 200 ), -- Randomized horizontal velocity.
		Random( 700, 1500 ) -- Randomized vertical velocity.
	)
end

GameScreenshake( 15 ) -- Applies a screen shake of intensity 15.
```

## Key Attributes

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `count`          | Number of meteors to spawn (randomly between 1 and 3).                   |
| `pos_x`, `pos_y` | Entity's current position, used as the base for meteor spawning.         |
| `Random()`       | Used extensively to introduce variability in spawn count, position, and velocity. |
| `shoot_projectile` | The core function for spawning projectile entities.                      |
| `meteor_green.xml` | The specific projectile entity file defining the meteor's behavior.      |
| `GameScreenshake`| Visual feedback to the player indicating an event has occurred.            |