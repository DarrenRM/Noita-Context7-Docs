---
title: Magic Shield Start Projectile
category: scripts
---

# Magic Shield Start Projectile

This script defines the behavior for the initial projectile that spawns the "magic shield" effect. It creates multiple smaller "magic shield part" projectiles around the initial projectile's location.

## Key Attributes and Behavior

*   **Projectile Spawning:** This script is attached to a projectile entity. Its primary function is to spawn other projectiles.
*   **Number of Parts:** It spawns a configurable number of `magic_shield_part.xml` projectiles.
*   **Angular Distribution:** The spawned parts are distributed in a circular pattern around the initial projectile.
*   **Random Rotation:** Each spawned part receives a random rotation value, with a bias against very small rotations.
*   **Shooter Identification:** It attempts to identify the entity that shot this projectile to pass this information to the spawned parts. If the shooter is not found, it searches for the closest "hittable" entity.
*   **Self-Destruction:** After spawning the parts, the initial projectile entity is killed.

## Core Logic Breakdown

### Initialization

1.  **Entity and Position:** Retrieves the current entity ID and its position (`pos_x`, `pos_y`).
2.  **Spawning Parameters:**
    *   `how_many`: Determines the number of shield parts to spawn (default is 4).
    *   `angle_inc`: Calculates the angular increment between spawned parts.
    *   `theta`: Initializes the starting angle, influenced by game frames for a dynamic effect.
    *   `length`: Defines the distance from the center at which parts are spawned.
3.  **Random Seed:** Sets a random seed based on the projectile's position and ID for deterministic randomness.
4.  **Rotation Calculation:**
    *   Generates a random `rotation` value between -12 and 12.
    *   Ensures the `rotation` is not too close to zero (less than 5).
    *   Introduces a small chance (1 in 20) for a significantly larger rotation (40).

### Shooter Identification

1.  **Retrieve Shooter:** Attempts to get the `mWhoShot` component from the projectile.
2.  **Fallback:** If `mWhoShot` is `NULL_ENTITY`, it searches for the closest entity with the "hittable" tag.

### Spawning Shield Parts

1.  **Conditional Spawning:** The loop to spawn parts only executes if a valid `shooter_id` is found.
2.  **Loop:** Iterates `how_many` times to spawn each shield part.
3.  **Position Calculation:** Calculates the `new_x` and `new_y` coordinates for each part based on `theta` and `length`.
4.  **Projectile Creation:** Uses `shoot_projectile_from_projectile` to spawn a `magic_shield_part.xml` at the calculated position.
5.  **Variable Storage:** Adds `VariableStorageComponent` to each spawned part to store:
    *   `angle`: The `theta` value at which it was spawned.
    *   `rot`: The calculated `rotation` value.
    *   `owner`: The `shooter_id` of the original projectile.
6.  **Angle Increment:** Updates `theta` for the next part.

### Cleanup

1.  **Entity Kill:** The original `magic_shield_start` projectile entity is removed from the game.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local how_many = 4
local angle_inc = ( 2 * 3.14159 ) / how_many
local theta = math.rad(6)-GameGetFrameNum() / 10.0
local length = 16

SetRandomSeed( pos_x * entity_id, pos_y * entity_id )

local rotation = Random(-12, 12)

while (math.abs(rotation) < 5) do
	rotation = Random(-12, 12)
end

if ( Random( 1, 20 ) == 5 ) then
	rotation = 40
end

local shooter_id = 0

edit_component( entity_id, "ProjectileComponent", function(comp,vars)
	shooter_id = ComponentGetValue2( comp, "mWhoShot" )
end)

if ( shooter_id == NULL_ENTITY ) then
	shooter_id = EntityGetClosestWithTag( pos_x, pos_y, "hittable" )
end

if ( shooter_id ~= nil ) and ( shooter_id ~= NULL_ENTITY ) then
	for i=1,how_many do
		local new_x = pos_x + math.cos( theta ) * length
		local new_y = pos_y + math.sin( theta ) * length
		
		local part_id = shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/magic_shield_part.xml", new_x, new_y, 0, 0 )
		
		EntityAddComponent( part_id, "VariableStorageComponent", 
			{
				name = "angle",
				value_float = theta,
			})
			
		EntityAddComponent( part_id, "VariableStorageComponent", 
			{
				name = "rot",
				value_int = rotation,
			})
			
		EntityAddComponent( part_id, "VariableStorageComponent", 
			{
				name = "owner",
				value_int = shooter_id,
			})
			
		theta = theta + angle_inc
	end
end

EntityKill( entity_id )
```