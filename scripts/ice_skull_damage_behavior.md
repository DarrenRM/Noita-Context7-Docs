---
title: Ice Skull Damage Behavior
category: scripts
---

# Ice Skull Damage Behavior

This script defines the behavior of an "Ice Skull" entity when it receives damage. Specifically, it triggers the spawning of ice projectiles in a circular pattern around the entity.

## Key Functionality

### `damage_received( damage, desc, entity_who_caused, is_fatal )`

This function is called when the entity takes damage.

*   **`damage`**: The amount of damage received.
*   **`desc`**: A description of the damage source.
*   **`entity_who_caused`**: The ID of the entity that caused the damage.
*   **`is_fatal`**: A boolean indicating if the damage is fatal.

### Projectile Spawning Logic

*   **Self-Damage Prevention**: The script checks if the damage was caused by the entity itself and returns if so, preventing self-inflicted projectile spawning.
*   **Fire Rate Limiting**: Uses `script_wait_frames( entity_id, 10 )` to ensure projectiles are only fired every 10 frames, controlling the rate of fire.
*   **Projectile Pattern**:
    *   Fires a fixed number of projectiles (`how_many = 12`).
    *   These projectiles are distributed evenly in a circle around the entity.
    *   Each projectile is of type `data/entities/projectiles/ice.xml`.
    *   The `length` variable determines the initial velocity magnitude of the projectiles.

## Core Attributes/Elements

*   **`entity_id`**: The unique identifier of the entity receiving damage.
*   **`pos_x`, `pos_y`**: The current position of the entity.
*   **`how_many`**: The number of projectiles to spawn (12).
*   **`angle_inc`**: The angular increment between projectiles, calculated to ensure a full circle.
*   **`length`**: The magnitude of the velocity applied to each projectile.
*   **`shoot_projectile()`**: The core function used to spawn projectiles.

```lua
dofile_once("data/scripts/lib/utilities.lua")

function damage_received( damage, desc, entity_who_caused, is_fatal )
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )

	if( entity_who_caused == entity_id ) then return end

	-- check that we're only shooting every 10 frames
	if script_wait_frames( entity_id, 10 ) then  return  end

	local how_many = 12
	local angle_inc = ( 2 * 3.14159 ) / how_many
	local theta = 0
	local length = 100

	for i=1,how_many do
		local vel_x = math.cos( theta ) * length
		local vel_y = math.sin( theta ) * length
		theta = theta + angle_inc

		shoot_projectile( entity_id, "data/entities/projectiles/ice.xml", pos_x, pos_y, vel_x, vel_y )
	end
end
```