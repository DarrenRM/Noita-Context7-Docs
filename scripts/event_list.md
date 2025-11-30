---
title: event_list
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/streaming_integration/event_list.lua
---

# event_list

This `event_list.lua` file defines a collection of "streaming events" for the game Noita. These events are designed to be triggered dynamically, likely in response to player actions, game state changes, or potentially viewer interaction in a streaming context. Each event has a unique identifier, descriptive text, an icon, a weight (influencing its probability of being chosen), a "kind" (categorizing its impact), and an `action` function that dictates what happens in the game when the event is activated. This file is crucial for adding dynamic and unpredictable elements to the gameplay experience.

## File Structure

The file is structured as a Lua script that defines a global table named `streaming_events`. This table contains a list of individual event definitions. Each event definition is itself a Lua table with the following key-value pairs:

*   **`id`**: A unique string identifier for the event (e.g., `"HEALTH_PLUS"`, `"SPEEDY_ENEMIES"`).
*   **`ui_name`**: A string representing the localized name of the event, often referencing a translation key (e.g., `"$streamingevent_health_plus"`).
*   **`ui_description`**: A string representing the localized description of the event, also referencing translation keys (e.g., `"$streamingeventdesc_health_plus"`).
*   **`ui_icon`**: A string path to the image file used for the event's icon in the user interface.
*   **`ui_author`**: A string indicating the creator of the event, often `"Nolla Games"` for official events.
*   **`weight`**: A numerical value (float) that influences the probability of this event being selected over others. Higher weights mean a higher chance.
*   **`kind`**: A numerical constant (defined earlier in the script) that categorizes the event's impact:
    *   `STREAMING_EVENT_AWFUL = 0`
    *   `STREAMING_EVENT_BAD = 1`
    *   `STREAMING_EVENT_NEUTRAL = 2`
    *   `STREAMING_EVENT_GOOD = 3`
    *   `STREAMING_EVENT_AUTHOR_NOLLAGAMES = "Nolla Games"` (This appears to be a string constant, not a numerical kind, but is used for the `ui_author` field).
*   **`action`**: A Lua function that contains the game logic to be executed when this event is triggered. This function typically takes an `event` argument, which might contain further details about the event's context.

The script also includes several `dofile_once` and `dofile` statements at the beginning, indicating that it relies on other utility and game helper scripts.

## Key Patterns

*   **Event Categorization**: The `kind` field provides a clear way to group events by their general impact (good, bad, neutral, awful).
*   **Player-Centric Actions**: Many events target the player(s) directly, modifying their health, speed, or applying status effects.
*   **Enemy Manipulation**: A significant number of events affect enemies, altering their behavior, stats, or applying effects.
*   **Entity Spawning**: Some events involve loading and spawning new entities (e.g., `rain_barrel.xml`, `gravity_field.xml`) into the game world.
*   **UI Integration**: The `ui_name`, `ui_description`, and `ui_icon` fields highlight the integration of these events with the game's user interface, suggesting they are presented to the player or viewers.
*   **Lua Functions for Logic**: The core of each event's effect is defined by a Lua anonymous function, allowing for complex and dynamic game modifications.
*   **Commented-Out Entries**: The presence of commented-out event definitions (e.g., `[[ ... ]]`) suggests that this file might be a work in progress or contains historical data.

## Sample Entries

Here are a few representative examples from the provided samples:

**1. `HEALTH_PLUS` Event:**

```lua
	{
		id = "HEALTH_PLUS",
		ui_name = "$streamingevent_health_plus",
		ui_description = "$streamingeventdesc_health_plus",
		ui_icon = "data/ui_gfx/streaming_event_icons/health_plus.png",
		ui_author = STREAMING_EVENT_AUTHOR_NOLLAGAMES,
		weight = 1.0,
		kind = STREAMING_EVENT_GOOD,
		action = function(event)
			for i,entity_id in ipairs( get_players() ) do
				local damagemodels = EntityGetComponent( entity_id, "DamageModelComponent" )
				
				local max_hp = 0
				local hp = 0
				
				if( damagemodels ~= nil ) then
					for a,damagemodel in ipairs(damagemodels) do
						max_hp = ComponentGetValue2( damagemodel, "max_hp" )
						hp = ComponentGetValue2( damagemodel, "hp" )
						hp = math.min( hp + 3.2, max_hp )
						
						ComponentSetValue2( damagemodel, "hp", hp )
					end
				end
			end
		end,
	},
```

*   **Explanation**: This event is categorized as `STREAMING_EVENT_GOOD`. When triggered, it iterates through all players, finds their `DamageModelComponent`, and increases their current HP by 3.2, capped by their maximum HP.

**2. `SPEEDY_ENEMIES` Event:**

```lua
	{
		id = "SPEEDY_ENEMIES",
		ui_name = "$streamingevent_speedy_enemies",
		ui_description = "$streamingeventdesc_speedy_enemies",
		ui_icon = "data/ui_gfx/streaming_event_icons/speedy_enemies.png",
		ui_author = STREAMING_EVENT_AUTHOR_NOLLAGAMES,
		weight = 1.0,
		kind = STREAMING_EVENT_BAD,
		action = function(event)
			for _,enemy in pairs(get_enemies_in_radius(400)) do
				local game_effect_comp,game_effect_entity = GetGameEffectLoadTo( enemy, "MOVEMENT_FASTER_2X", false )
				if (game_effect_comp ~= nil) and (game_effect_entity ~= nil) then
					ComponentSetValue( game_effect_comp, "frames", "-1" )
					add_icon_above_head( game_effect_entity, "data/ui_gfx/status_indicators/movement_faster.png", event )
				end
			end
		end,
	},
```

*   **Explanation**: This `STREAMING_EVENT_BAD` event targets enemies within a 400-unit radius. It applies a "MOVEMENT\_FASTER\_2X" game effect to them, making them move twice as fast, and displays a status icon above their heads. The effect is set to last indefinitely (`"-1"` frames).

**3. `RAIN_BARREL` Event:**

```lua
	{
		id = "RAIN_BARREL",
		ui_name = "$streamingevent_rain_barrel",
		ui_description = "$streamingeventdesc_rain_barrel",
		ui_icon = "data/ui_gfx/streaming_event_icons/protect_enemies.png",
		ui_author = STREAMING_EVENT_AUTHOR_NOLLAGAMES,
		weight = 1.0,
		kind = STREAMING_EVENT_NEUTRAL,
		action = function(event)
			for i,entity_id in pairs( get_players() ) do
				local x, y = EntityGetTransform( entity_id )
				
				EntityLoad( "data/scripts/streaming_integration/entities/rain_barrel.xml", x, y )
			end
		end,
	},
```

*   **Explanation**: This `STREAMING_EVENT_NEUTRAL` event spawns a "rain barrel" entity. For each player, it gets their current position and then loads the `rain_barrel.xml` entity at that location.

## Reference

This file contains 2350 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/streaming_integration/event_list.lua).

---