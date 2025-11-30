---
title: Sunstone Conversion Building
category: scripts
---

# Sunstone Conversion Building

This script defines a building that converts "seed_a" items into a "sunstone" pickup and a "giga explosion" projectile. It also triggers specific music and game messages upon successful conversion.

## Key Functionality

*   **Item Conversion:** Detects nearby entities tagged with "seed_a".
*   **Conversion Criteria:** Only converts items that are not carried in an inventory or wand (i.e., are world entities).
*   **Spawned Items:** Upon conversion, spawns:
    *   `data/entities/items/pickup/sun/sunstone.xml`
    *   `data/entities/projectiles/deck/explosion_giga.xml`
*   **Music Trigger:** Fades out current music and plays a specific "dark\_01" music track.
*   **Game Message:** Displays an important game message indicating a new step.

## Core Logic

The script iterates through entities within a 70-unit radius of the building. If an entity is tagged "seed\_a" and is a root entity (not part of another entity), it is converted.

```lua
dofile_once("data/scripts/lib/utilities.lua")
dofile( "data/scripts/gun/gun_actions.lua" )

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- convert items
local converted = false

for _,id in pairs(EntityGetInRadiusWithTag(pos_x, pos_y, 70, "seed_a")) do
	-- make sure item is not carried in inventory or wand
	if EntityGetRootEntity(id) == id then
		local x,y = EntityGetTransform(id)
		EntityLoad("data/entities/items/pickup/sun/sunstone.xml", x, y)
		EntityLoad("data/entities/projectiles/deck/explosion_giga.xml", x, y)
		EntityKill(id)
		converted = true
	end
end

if converted then
	GameTriggerMusicFadeOutAndDequeueAll( 3.0 )
	GameTriggerMusicEvent( "music/oneshot/dark_01", true, pos_x, pos_y )
	
	GamePrintImportant( "$log_new_step", "$logdesc_new_step" )
end
```

## Key Attributes/Elements

| Attribute/Element        | Description                                                                 |
| :----------------------- | :-------------------------------------------------------------------------- |
| `EntityGetInRadiusWithTag` | Detects entities within a specified radius and with a given tag.            |
| `radius`                 | 70 units.                                                                   |
| `tag`                    | "seed\_a".                                                                  |
| `EntityGetRootEntity`    | Checks if the entity is a standalone world entity.                          |
| `EntityLoad`             | Spawns new entities at specified coordinates.                               |
| `EntityKill`             | Removes an entity from the game.                                            |
| `GameTriggerMusicFadeOutAndDequeueAll` | Fades out all currently playing music.                                |
| `fade_duration`          | 3.0 seconds.                                                                |
| `GameTriggerMusicEvent`  | Triggers a specific music event.                                            |
| `music_event`            | "music/oneshot/dark\_01".                                                   |
| `GamePrintImportant`     | Displays a critical message to the player.                                  |
| `message_key`            | "$log\_new\_step".                                                          |
| `message_description_key`| "$logdesc\_new\_step".                                                      |