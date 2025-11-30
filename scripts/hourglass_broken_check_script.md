---
title: Hourglass Broken Check Script
category: scripts
---

# Hourglass Broken Check Script

This script is designed to detect if a "broken" hourglass entity is still present in the game world. If the hourglass is no longer detected, it triggers a visual effect and sound, and then cleans up any associated "hourglass_entity" tags.

## Key Functionality

*   **Entity Detection:** The script uses raycasting to check for the presence of platforms around the hourglass's position. This is a proxy for checking if the hourglass itself (or its supporting structure) is still intact.
*   **Broken State Trigger:** If the raycasts fail to detect platforms on either the left or right side, the hourglass is considered "broken."
*   **Visual and Audio Feedback:** Upon detecting a broken state, the script spawns a `crumbling_earth_effect.xml` entity and plays a specific sound effect (`player_projectiles/crumbling_earth/create`).
*   **Entity Cleanup:** The script iterates through all entities tagged with "hourglass\_entity" within a certain radius and removes them, effectively cleaning up any remnants of the broken hourglass.

## Core Logic

The script primarily relies on the `RaytracePlatforms` function to determine the integrity of the hourglass's surroundings.

```lua
local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform(entity_id)

-- Adjust y position for raycasting
y = y + 26

-- Define raycast start and end points for left and right sides
local left_x1 = x - 28
local left_x2 = x - 36
local right_x1 = x + 28
local right_x2 = x + 38

-- Check if platforms are detected on both sides
if RaytracePlatforms(left_x1, y, left_x2, y) == false or RaytracePlatforms(right_x1, y, right_x2, y) == false then
	-- Trigger effects if broken
	EntityLoad("data/entities/projectiles/deck/crumbling_earth_effect.xml", x, y + 46)
	GamePlaySound( "data/audio/Desktop/projectiles.snd", "player_projectiles/crumbling_earth/create", x, y )

	-- Clean up associated hourglass entities
	for _,v in pairs(EntityGetInRadiusWithTag(x, y, 150, "hourglass_entity")) do
		EntityKill(v)
	end
end
```

## Key Attributes/Elements

*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity running this script.
*   **`EntityGetTransform(entity_id)`**: Gets the X and Y coordinates of the entity.
*   **`RaytracePlatforms(x1, y1, x2, y2)`**: Performs a raycast to check for platforms between the given coordinates. Returns `true` if a platform is hit, `false` otherwise.
*   **`EntityLoad(entity_path, x, y)`**: Spawns a new entity at the specified coordinates.
*   **`GamePlaySound(sound_file, sound_name, x, y)`**: Plays a sound effect.
*   **`EntityGetInRadiusWithTag(x, y, radius, tag)`**: Finds all entities within a given radius that have a specific tag.
*   **`EntityKill(entity_id)`**: Destroys an entity.
*   **`"hourglass_entity"` (Tag)**: A tag used to identify entities related to the hourglass that need to be cleaned up.
*   **`"data/entities/projectiles/deck/crumbling_earth_effect.xml"`**: The entity spawned to visually represent the crumbling effect.
*   **`"data/audio/Desktop/projectiles.snd"`**: The sound file containing the crumbling earth sound.