---
title: Fun Room Trigger
category: scripts
---

# Fun Room Trigger

This script defines a trigger that activates special effects and material conversions when a player unit is detected within a certain radius, alongside a "tripping_extreme" tag.

## Key Functionality

This script's primary purpose is to detect specific conditions and trigger a set of in-game events.

### Trigger Conditions

*   **Player Proximity:** The script checks for the presence of a "player_unit" within a `radius` of 24 units from the entity's position.
*   **Special Tag Presence:** It also requires the presence of an entity with the tag "tripping_extreme" within the same radius.

### Activated Effects

When both trigger conditions are met, the following actions occur:

*   **Sound Effect:** A specific sound event (`event_cues/fungal_effect/create`) is played.
*   **Material Conversion:**
    *   `rock_static_trip_secret2` is converted to `templebrick_golden_static` everywhere.
    *   `rock_static_trip_secret` is converted to `material_rainbow` everywhere.
*   **Screen Shake:** A screen shake effect with an intensity of 80 is applied.
*   **Entity Destruction:** The entity executing this script is destroyed.

## Key Attributes

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `radius`         | The detection radius for player and tagged entities (default: 24).     |
| `"player_unit"`  | The tag identifying the player entity.                                   |
| `"tripping_extreme"` | A specific tag required for the trigger to activate.                     |
| `GamePlaySound`  | Plays a sound effect upon trigger activation.                            |
| `ConvertMaterialEverywhere` | Converts specified materials across the game world.                  |
| `GameScreenshake` | Applies a screen shake effect.                                           |
| `EntityKill`     | Destroys the entity running the script after activation.                 |

## Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )
local radius = 24

local targets = EntityGetInRadiusWithTag( x, y, radius, "player_unit" )
local targets2 = EntityGetInRadiusWithTag( x, y, radius, "tripping_extreme" )

if ( #targets > 0 ) and ( #targets2 > 0 ) then
	GamePlaySound( "data/audio/Desktop/event_cues.bank", "event_cues/fungal_effect/create", x, y )
	ConvertMaterialEverywhere( CellFactory_GetType( "rock_static_trip_secret2" ), CellFactory_GetType( "templebrick_golden_static" ) )
	ConvertMaterialEverywhere( CellFactory_GetType( "rock_static_trip_secret" ), CellFactory_GetType( "material_rainbow" ) )
	GameScreenshake( 80, x, y )
	
	EntityKill( entity_id )
end
```