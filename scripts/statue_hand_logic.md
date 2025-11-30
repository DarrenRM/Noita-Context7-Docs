---
title: Statue Hand Logic
category: scripts
---

# Statue Hand Logic

This script defines the behavior for modified statue hands in Noita, specifically handling their destruction and the subsequent summoning of monks and a broken portal.

## Core Functionality

The primary function `mark_as_complete()` is triggered when a statue hand is interacted with (e.g., kicked) or destroyed. It checks for specific tags and game flags to determine which stage of destruction the statue is in and executes the appropriate actions.

### `mark_as_complete()`

This function orchestrates the destruction sequence of the statue hand.

*   **Entity Identification:** Retrieves the current entity's ID and its position.
*   **`disappear(count)` Helper Function:**
    *   Kills the current statue hand entity.
    *   Loads a visual effect entity (`statue_hand_fx.xml`) at the statue's position.
    *   Spawns a specified number of `monk.xml` entities around the statue's position.
*   **Conditional Logic:**
    *   **Stage 3 Destruction:** If the statue has the tag `"statue_hand_3"` and the flag `"statue_hands_destroyed_2"` is active, it sets `"statue_hands_destroyed_3"`, loads a `"summon_portal_broken.xml"` item, and calls `disappear(3)`.
    *   **Stage 2 Destruction:** If the statue has the tag `"statue_hand_2"` and the flag `"statue_hands_destroyed_1"` is active, it sets `"statue_hands_destroyed_2"` and calls `disappear(2)`.
    *   **Stage 1 Destruction:** If the statue has the tag `"statue_hand_1"`, it sets `"statue_hands_destroyed_1"` and calls `disappear(1)`.

### `physics_body_modified(is_destroyed)`

This function is a callback for physics body modifications. Currently, it's commented out but intended to call `mark_as_complete()` if the entity is destroyed.

### `kick()`

This function is a simple wrapper that calls `mark_as_complete()`, allowing the statue to be destroyed and its associated effects triggered by a kick action.

## Key Attributes and Elements

*   **Entity Tags:**
    *   `"statue_hand_1"`
    *   `"statue_hand_2"`
    *   `"statue_hand_3"`
    These tags differentiate the stages of the statue hand.
*   **Game Flags:**
    *   `"statue_hands_destroyed_1"`
    *   `"statue_hands_destroyed_2"`
    *   `"statue_hands_destroyed_3"`
    These flags track the progression of statue destruction across the game.
*   **Entity Loading:**
    *   `"data/entities/buildings/statue_hand_fx.xml"`: Visual effect for the destroyed statue.
    *   `"data/entities/animals/monk.xml"`: The monk entities that are summoned.
    *   `"data/entities/items/pickup/summon_portal_broken.xml"`: The broken portal item that appears after the final statue is destroyed.
*   **Functions:**
    *   `mark_as_complete()`: The main logic handler.
    *   `disappear(count)`: A helper for entity destruction and spawning.
    *   `physics_body_modified(is_destroyed)`: Physics callback.
    *   `kick()`: Trigger for destruction.

```lua
dofile_once("data/scripts/lib/utilities.lua")

function mark_as_complete()
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )

	local function disappear(count)
		EntityKill(entity_id)
		EntityLoad("data/entities/buildings/statue_hand_fx.xml", pos_x, pos_y)
		for i=1, count do
			EntityLoad("data/entities/animals/monk.xml", pos_x + i%2*4, pos_y - (i-1) * 10)
		end
	end

	if EntityHasTag(entity_id, "statue_hand_3") and GameHasFlagRun("statue_hands_destroyed_2") then
		GameAddFlagRun("statue_hands_destroyed_3")
		EntityLoad("data/entities/items/pickup/summon_portal_broken.xml", pos_x, pos_y - 5)
		disappear(3)
	elseif EntityHasTag(entity_id, "statue_hand_2") and GameHasFlagRun("statue_hands_destroyed_1") then
		GameAddFlagRun("statue_hands_destroyed_2")
		disappear(2)
	elseif EntityHasTag(entity_id, "statue_hand_1") then
		GameAddFlagRun("statue_hands_destroyed_1")
		disappear(1)
	end
end

function physics_body_modified(is_destroyed)
	--if is_destroyed then mark_as_complete() end
end

function kick()
	mark_as_complete()
end
```