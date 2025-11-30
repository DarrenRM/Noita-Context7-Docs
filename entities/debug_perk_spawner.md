---
title: Debug Perk Spawner
category: entities
---

# Debug Perk Spawner

This entity provides a debug tool for spawning perks directly into the game world. It creates a simple GUI interface that lists available perks, allowing the player to select and spawn one at their current location.

## Core Functionality

The primary purpose of this entity is to facilitate testing and debugging of perks by enabling their on-demand spawning.

### Key Attributes/Elements

*   **`gui_frame_fn`**: This function handles the creation and updating of the in-game GUI. It's responsible for drawing the perk list and handling button clicks.
*   **`perk_button_action(i)`**: A helper function that defines the behavior when a perk button is clicked. It retrieves the player's position, attempts to find the player entity, and then calls `perk_spawn` to create the selected perk.
*   **`perk_list`**: This global variable (presumably defined elsewhere, likely in `data/scripts/perks/perk.lua`) contains a list of all available perks, each with an `id` and `ui_name`.
*   **`GuiCreate()`**: Initializes a new GUI object.
*   **`GuiLayoutBeginVertical()` / `GuiLayoutEnd()`**: Functions used to organize GUI elements in a vertical layout.
*   **`GuiText()`**: Displays text on the GUI.
*   **`GuiButton()`**: Creates a clickable button on the GUI.
*   **`GamePrint()`**: Displays a message in the game's console.
*   **`GameGetCameraPos()`**: Gets the current camera position, used to determine the player's approximate location.
*   **`EntityGetClosestWithTag()`**: Finds the closest entity with a specific tag (e.g., "player\_unit").
*   **`EntityGetTransform()`**: Retrieves the position and rotation of an entity.
*   **`perk_spawn(x, y, perk_id)`**: The core function that spawns a perk at the specified coordinates with the given perk ID.
*   **`GuiDestroy()`**: Cleans up and removes the GUI.
*   **`EntityKill()`**: Destroys the entity that owns this script.
*   **`async_loop()`**: A utility for running asynchronous game loops, used here to continuously update the GUI.

## Usage

1.  **Spawn the Debug Entity**: This entity needs to be placed in the game world for its functionality to be accessible.
2.  **Interact with the GUI**: Upon interaction (likely by the player), a GUI window will appear.
3.  **Select a Perk**: The GUI displays a list of available perks. Clicking on a perk's name will attempt to spawn it.
4.  **Perk Spawning**: The selected perk will be spawned at the player's current location (or the player's entity's location if found).
5.  **Close the GUI**: A "Close" button is available to dismiss the perk selection interface.

## Technical Details

The script utilizes Noita's Lua API for GUI creation, entity manipulation, and game state access. It dynamically generates buttons for each perk and handles the logic for spawning them. The `async_loop` ensures the GUI remains responsive and updates correctly.

```lua
dofile( "data/scripts/lib/coroutines.lua" )
dofile( "data/scripts/lib/utilities.lua" )
dofile( "data/scripts/perks/perk.lua")

local gui_frame_fn = nil
local gui = GuiCreate()

gui_frame_fn = function()
	local destroy = false
	local hax_btn_id = 123
	local num_perks = #perk_list

	local perk_button_action = function ( i )
		if GuiButton( gui, 0, 0, perk_list[i].ui_name, hax_btn_id+i ) then
			GamePrint( "DEBUG - attempting to spawn " .. perk_list[i].id .. " at player location" )

			local x, y = GameGetCameraPos()
			local player_entity = EntityGetClosestWithTag( x, y, "player_unit")
			if( player_entity ~= 0 ) then
				x, y = EntityGetTransform( player_entity )
			end
			perk_spawn( x, y - 8, perk_list[i].id )
		end
	end

	GuiLayoutBeginVertical( gui, 1, 0 )
	GuiText( gui, 0,0, "Select a perk to spawn at player location" )
	if GuiButton( gui, 0, 0, "Close", hax_btn_id ) then
		print("2")
		destroy = true
	end
	GuiLayoutEnd( gui)

	-- column 1
	GuiLayoutBeginVertical( gui, 5, 4 )
	for i=1,31 do
		if i > num_perks then
			break
		end
		perk_button_action( i )
	end
	GuiLayoutEnd( gui )

	-- column 2
	GuiLayoutBeginVertical( gui, 35, 4 )
	for i=32,63 do
		if i > num_perks then
			break
		end
		perk_button_action( i )
	end
	GuiLayoutEnd( gui )

	-- column 3
	GuiLayoutBeginVertical( gui, 65, 4 )
	for i=63,94 do
		if i > num_perks then
			break
		end
		perk_button_action( i )
	end
	GuiLayoutEnd( gui )

	if destroy then
		GuiDestroy( gui )
		gui_frame_fn = nil
		gui = nil
		EntityKill( GetUpdatedEntityID() )
	end
end

async_loop(function()
	if gui ~= nil then
		GuiStartFrame( gui )
	end

	if gui_frame_fn ~= nil then
		gui_frame_fn()
	end

	wait(0)
end)
```