---
title: Laser Gun Building Script
category: scripts
---

---

# Laser Gun Building Script

This script controls the behavior of the Laser Gun building entity in Noita. It manages the firing mechanism, including a randomized timing delay before firing a projectile.

## Key Components and Logic

### Entity Initialization

-   **`GetUpdatedEntityID()`**: Retrieves the unique ID of the current entity.
-   **`EntityGetTransform( entity_id )`**: Gets the position (x, y) of the entity.
-   **`SetRandomSeed( x, y )`**: Initializes the random number generator based on the entity's position for consistent randomness.

### Firing Mechanism

-   **`timing`**: A variable stored within the `VariableStorageComponent` that controls the delay between shots.
    -   Initialized to `-1` if not present.
    -   If `timing` is `-1`, it's randomly set between 0 and 10.
    -   If `timing` is greater than or equal to 0, it's incremented.
    -   When `timing` reaches `11`, it resets to `0`, and the `fire` flag is set to `true`.
-   **`fire`**: A boolean flag that determines if a projectile should be shot.

### Projectile Firing

-   **`shoot_projectile()`**: A function (assumed to be defined elsewhere, likely in `utilities.lua`) that spawns a projectile.
    -   **`entity_id`**: The ID of the entity firing the projectile.
    -   **`"data/entities/projectiles/laser_lasergun.xml"`**: The XML file defining the projectile's properties.
    -   **`x, y + 8`**: The spawn position of the projectile, slightly above the building's center.
    -   **`vel_x, vel_y`**: The velocity of the projectile (0 horizontal, 1000 vertical).

## VariableStorageComponent Usage

The script heavily relies on the `VariableStorageComponent` to store and manage the `timing` variable. This allows the building's state to persist and be modified across game ticks.

```lua
-- Example of how timing is managed:
local timing = -1
local fire = false

local variablestorages = EntityGetComponent( entity_id, "VariableStorageComponent" )

if ( variablestorages ~= nil ) then
	for j,storage_id in ipairs(variablestorages) do
		local var_name = ComponentGetValue( storage_id, "name" )
		if ( var_name == "timing" ) then
			timing = ComponentGetValueInt( storage_id, "value_int" )

			if (timing == -1) then
				timing = Random( 0, 10 )
			elseif (timing > -1) then
				timing = timing + 1
			end

			if (timing == 11) then
				timing = 0
				fire = true
			end

			ComponentSetValue( storage_id, "value_int", timing )
		end
	end
end

if fire then
	local vel_x = 0
	local vel_y = 1000
	shoot_projectile( entity_id, "data/entities/projectiles/laser_lasergun.xml", x, y + 8, vel_x, vel_y )
end
```