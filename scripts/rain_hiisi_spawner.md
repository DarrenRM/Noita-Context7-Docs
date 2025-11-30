---
title: Rain Hiisi Spawner
category: scripts
---

# Rain Hiisi Spawner

This script is responsible for spawning various types of Hiisi enemies in a localized area, simulating a "rain" of enemies. It's designed to be triggered by an entity and will attempt to find suitable locations around the spawner's position.

## Key Functionality

*   **Randomized Spawning:** Spawns a random number of Hiisi (1 to 3) per execution.
*   **Enemy Type Selection:** Chooses from a predefined list of Hiisi types.
*   **Location Finding:** Attempts to find valid spawn points that are not too close to the spawner and are not obstructed by walls.
*   **Visual/Audio Feedback:** Triggers a screenshake upon completion.

## Core Attributes

### Spawn Parameters

*   `count`: Determines the number of Hiisi to spawn (randomly between 1 and 3).
*   `types`: A table containing the names of the Hiisi entities that can be spawned.

```lua
local count = Random( 1, 3 )
local types = { "zombie", "miner", "shotgunner", "scavenger_smg", "scavenger_grenade", "scavenger_heal", "scavenger_mine", "sniper" }
```

### Location Finding Logic

The script uses a raycasting system to ensure spawned enemies are not inside walls and are at a reasonable distance from the spawner.

*   `raycasts`: Number of rays cast to check for obstructions.
*   `dir`: The angular separation between rays.
*   `length`: The distance each ray is cast.
*   `limit`: A safety counter to prevent infinite loops if a suitable spot cannot be found.
*   `off_x`, `off_y`: The calculated offset from the spawner's position for a potential spawn point.
*   `wall`: A boolean indicating if a raycast hit a surface.
*   `failed`: A boolean indicating if the location finding process failed after multiple attempts.

```lua
local raycasts = 4
local dir = ( math.pi * 2.0 ) / raycasts
local length = 8

-- ... inside the while loop ...
local limit = 0
local off_x,off_y = 0,0
local wall = true
local failed = false

while ( math.abs( off_x ) + math.abs( off_y ) < 100 ) or wall do
    -- ... raycasting logic ...
    limit = limit + 1
    if ( limit > 20 ) then
        print( "Couldn't find a good spot" )
        wall = false
        failed = true
    end
end
```

### Entity Spawning

Once a suitable location is found, the script loads the specified Hiisi entity and an "empty circle" entity (likely for visual effect or collision).

*   `EntityLoad( "data/entities/animals/" .. entity .. ".xml", pos_x + off_x, pos_y + off_y )`: Spawns the chosen Hiisi.
*   `EntityLoad( "data/scripts/streaming_integration/entities/empty_circle_small.xml", pos_x + off_x, pos_y + off_y )`: Spawns a small empty circle.

```lua
if ( entity ~= nil ) and ( failed == false ) then
    EntityLoad( "data/entities/animals/" .. entity .. ".xml", pos_x + off_x, pos_y + off_y )
    EntityLoad( "data/scripts/streaming_integration/entities/empty_circle_small.xml", pos_x + off_x, pos_y + off_y )
end
```

## Visual/Audio Effects

*   `GameScreenshake( 10 )`: Triggers a screenshake with an intensity of 10.

## Modding Considerations

*   **Adding New Hiisi Types:** To spawn new Hiisi, add their entity names to the `types` table. Ensure the corresponding `.xml` files exist in `data/entities/animals/`.
*   **Adjusting Spawn Density:** Modify the `count` variable or the range in `Random( 1, 3 )` to control how many enemies spawn.
*   **Tuning Location Finding:** Adjust `length`, `raycasts`, and the distance check `math.abs( off_x ) + math.abs( off_y ) < 100` to control where enemies can spawn and how far they are from the spawner.
*   **Custom Spawn Effects:** Replace or modify the `empty_circle_small.xml` entity load to add custom visual effects for the spawn.
*   **Screenshake Intensity:** Change the value in `GameScreenshake( 10 )` to alter the screenshake effect.