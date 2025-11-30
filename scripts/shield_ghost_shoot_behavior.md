---
title: Shield Ghost Shoot Behavior
category: scripts
---

# Shield Ghost Shoot Behavior

This script defines the behavior for a "Shield Ghost" entity in Noita, specifically its projectile-firing mechanism. It targets the nearest valid enemy within a certain range, checks for line of sight, and then fires a projectile with some scatter.

## Key Attributes and Behavior

### Targeting and Range
*   **`range`**: Defines the maximum distance (in pixels) the ghost will search for enemies.
    *   Value: `160`
*   **Targeting Logic**: The script iterates through entities within the specified `range` tagged as "mortal".
*   **Enemy Validation**:
    *   Must have a `GenomeDataComponent`.
    *   Must have a herd relation score greater than 90 with the ghost's root entity (indicating an enemy).
    *   Must *not* have a child entity tagged "shieldshot" (meaning it hasn't already been targeted by a shield shot).

### Projectile Mechanics
*   **`projectile_velocity`**: The speed at which the fired projectile travels.
    *   Value: `240`
*   **`scatter`**: The degree of random deviation applied to the projectile's trajectory.
    *   Value: `0.1`
*   **Projectile Type**: Fires `data/entities/projectiles/shieldshot_small.xml`.

### Line of Sight (LOS)
*   **`RaytraceSurfacesAndLiquiform`**: A check is performed to ensure there are no surfaces or liquids obstructing the path between the ghost and its target. If LOS is blocked, the ghost will not shoot.

### Firing Logic
1.  **Direction Calculation**: The script calculates the vector from the ghost's position to the target enemy's position.
2.  **Normalization**: The direction vector is normalized to a unit vector.
3.  **Scatter Application**: A random rotation is applied to the normalized direction vector based on the `scatter` value.
4.  **Velocity Application**: The scattered direction vector is multiplied by `projectile_velocity` to determine the final projectile velocity.
5.  **Projectile Firing**: The `shoot_projectile` function is called to instantiate and launch the projectile.

### Cooldown and Timing
*   **`execute_every_n_frame`**: The script dynamically sets a component value to control the firing rate. This introduces a random delay between shots to prevent multiple ghosts from firing simultaneously.
    *   Base delay: `70` frames.
    *   Random addition: `Random(2)` frames.

```lua
-- Configuration variables
local range = 160
local projectile_velocity = 240
local scatter = 0.1

-- Get entity IDs and initial position
local entity_id = GetUpdatedEntityID()
local root_id = EntityGetRootEntity(entity_id)
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Variables for tracking the nearest enemy
local enemy = nil
local enemy_x, enemy_y = nil, nil
local min_dist = 9999

-- Iterate through entities within range to find a suitable target
for _,id in pairs(EntityGetInRadiusWithTag(pos_x, pos_y, range, "mortal")) do
	-- Check if the entity is a valid enemy
	if EntityGetComponent(id, "GenomeDataComponent") ~= nil and EntityGetHerdRelation(root_id, id) > 90 then
		local x, y = EntityGetFirstHitboxCenter( id )
		local dist = get_distance(pos_x, pos_y, x, y)

		-- Check if this enemy is closer than the current closest
		if dist < min_dist then
			local needs_healing = true
			local children = EntityGetAllChildren( id )
			if children ~= nil then
				for _, child_id in pairs( children ) do
					if EntityHasTag( child_id, "shieldshot" ) then
						needs_healing = false
						break
					end
				end
			end

			-- If the enemy needs healing (no shieldshot tag), select it
			if needs_healing then
				min_dist = dist
				enemy = id
				enemy_x = x
				enemy_y = y
				-- Optimization: break early once a valid, closer enemy is found
				break
			end
		end
	end
end

-- If no enemy was found, exit the script
if not enemy then return end

-- Check for line of sight to the target enemy
if RaytraceSurfacesAndLiquiform(pos_x, pos_y, enemy_x, enemy_y) then return end

-- Calculate direction vector towards the enemy
local vel_x, vel_y = vec_sub(enemy_x, enemy_y, pos_x, pos_y)
vel_x, vel_y = vec_normalize(vel_x, vel_y)

-- Apply random scatter to the direction
SetRandomSeed(pos_x + GameGetFrameNum(), pos_y)
vel_x, vel_y = vec_rotate(vel_x, vel_y, rand(-scatter, scatter))

-- Apply projectile velocity
vel_x, vel_y = vec_mult(vel_x, vel_y, projectile_velocity)

-- Shoot the projectile
shoot_projectile( root_id, "data/entities/projectiles/shieldshot_small.xml", pos_x, pos_y, vel_x, vel_y)

-- Set a random delay for the next shot
local comp_id = GetUpdatedComponentID()
if comp_id ~= 0 then
	ComponentSetValue(comp_id, "execute_every_n_frame", 70 + Random(2))
end
```