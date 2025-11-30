---
title: Beam From Sky Spell
category: scripts
---

# Beam From Sky Spell

This script defines the behavior for a spell that summons a powerful beam from the sky. It's designed to be a high-impact, visually striking spell with significant screen shake and a large particle effect.

## Core Functionality

The spell operates asynchronously, meaning it runs in the background without blocking the main game loop.

### Key Actions:

*   **Initialization:**
    *   Retrieves the spell's entity ID and its position.
    *   Plays a "beam from sky start" sound effect.
    *   Displays an important game message: "$log_beam_stone".
*   **Screen Shake Sequence:**
    *   Initiates a series of increasingly intense screen shakes to build anticipation and emphasize the impact.
*   **World Interaction:**
    *   Triggers a vertical "cut through world" effect at the spell's location, indicating a powerful impact.
    *   Plays a "beam from sky hit" sound effect at the impact point.
    *   Applies a final, very strong screen shake.
*   **Visual Effects:**
    *   Loads a large green "poof" particle effect at the impact location.
    *   Significantly increases the particle emission count for the spell's associated particle emitter, creating a dense visual effect.

## Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")
dofile_once("data/scripts/lib/coroutines.lua")

async(function ()
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )
	
	-- Initial messages and sound
	GamePrintImportant( "$log_beam_stone")
	GameEntityPlaySound( entity_id, "beam_from_sky_start" )
	wait( 60 ) -- Wait for 60 frames

	-- Screen shake sequence
	GameScreenshake( 10 )
	wait( 20 )
	GameScreenshake( 20 )
	wait( 20 )
	GameScreenshake( 30 )
	wait( 20 )
	
	GameScreenshake( 40 )
	wait( 20 )
	GameScreenshake( 60 )
	wait( 20 )
	GameScreenshake( 100 )
	wait( 20 )
	
	-- World interaction and final effects
	GameCutThroughWorldVertical( pos_x, -2147483647, pos_y, 40, 40 ) -- Vertical cut through the world
	EntitySetComponentsWithTagEnabled( entity_id, "enabled_in_world", true ) -- Enable components tagged "enabled_in_world"
	GamePlaySound( "data/audio/Desktop/misc.bank", "misc/beam_from_sky_hit", pos_x, pos_y ) -- Play impact sound
	GameScreenshake( 200 ) -- Maximum screen shake
    EntityLoad( "data/entities/particles/poof_green_huge.xml", pos_x, pos_y-5 ) -- Load large particle effect
	component_write( EntityGetFirstComponent( entity_id, "ParticleEmitterComponent"), { count_min=21000, count_max=21000, cosmetic_force_create=true } ) -- Maximize particle emission
end)
```

## Key Attributes and Elements

*   **`async(function () ... end)`**: Executes the spell's logic asynchronously.
*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the spell entity.
*   **`EntityGetTransform( entity_id )`**: Gets the X and Y coordinates of the spell.
*   **`GamePrintImportant( "$log_beam_stone")`**: Displays a significant message to the player.
*   **`GameEntityPlaySound( entity_id, "beam_from_sky_start" )`**: Plays the initial sound effect associated with the spell entity.
*   **`wait( frames )`**: Pauses script execution for a specified number of frames.
*   **`GameScreenshake( intensity )`**: Triggers a screen shake effect with a given intensity.
*   **`GameCutThroughWorldVertical( x, y_min, y_max, width, height )`**: Creates a visual effect of cutting through the game world vertically. The large negative `y_min` value suggests it cuts from the very top of the map.
*   **`EntitySetComponentsWithTagEnabled( entity_id, "enabled_in_world", true )`**: Activates components on the spell entity that are tagged as "enabled\_in\_world".
*   **`GamePlaySound( bank, sound_name, x, y )`**: Plays a specific sound effect at a given world position.
*   **`EntityLoad( xml_path, x, y )`**: Loads an entity (in this case, a particle effect) at specified coordinates.
*   **`component_write( component, properties )`**: Modifies properties of a specific component. Here, it targets a `ParticleEmitterComponent` to drastically increase particle count and ensure creation.
    *   **`count_min`, `count_max`**: Set to `21000` to create a very dense particle effect.
    *   **`cosmetic_force_create=true`**: Ensures the particles are created even if the game might otherwise optimize them away.