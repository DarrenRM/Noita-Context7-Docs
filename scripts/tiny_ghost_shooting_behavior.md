---
title: Tiny Ghost Shooting Behavior
category: scripts
---

# Tiny Ghost Shooting Behavior

This script defines the behavior for a "tiny ghost" entity in Noita, specifically its projectile-firing mechanism. It targets the nearest enemy, checks for line of sight, and dynamically selects projectile types and quantities based on the entity's lost health.

## Key Attributes and Behaviors

*   **Targeting Range:** `range` (default: 200 units) - The maximum distance at which the ghost will search for enemies.
*   **Projectile Velocity:** `projectile_velocity_min` (default: 570) to `projectile_velocity_max` (default: 630) - The speed range for fired projectiles.
*   **Shot Scatter:** `scatter` (initial: 0.15) - Controls the angular deviation of projectiles from the target direction. This value increases with each subsequent shot in a burst.
*   **Enemy Detection:**
    *   Searches for entities with the "mortal" tag within the `range`.
    *   Filters targets to ensure they have a `GenomeDataComponent` and are not of the same "herd relation" as the ghost.
    *   Prioritizes the closest valid enemy.
*   **Line of Sight (LOS) Check:** Uses `RaytraceSurfacesAndLiquiform` to ensure there are no obstacles between the ghost and its target before firing.
*   **Dynamic Projectile Selection:** The type and number of projectiles fired are determined by the ghost's lost health:
    *   **Low Lost HP (0-25):** `bullet` (1 shot)
    *   **Moderate Lost HP (25-50):** `bullet_heavy` (1 shot)
    *   **Significant Lost HP (50-100):** `spitter_tier_3` (1 shot)
    *   **Higher Lost HP Tiers:** Increase projectile count and/or upgrade projectile type (e.g., `bullet`, `bullet_heavy`, `spitter_tier_3`).
*   **Firing Mechanism:**
    *   Calculates the direction towards the target.
    *   Applies scatter to the projectile's velocity.
    *   Fires projectiles using `shoot_projectile`.
*   **Execution Delay:** `execute_every_n_frame` is set to a random value between 24 and 26 frames to stagger firing among multiple ghosts.

## Projectile Types and Lost HP Thresholds

| Lost HP Threshold | Projectile Type   | Projectile Count |
| :---------------- | :---------------- | :--------------- |
| 0 - 25            | `bullet`          | 1                |
| 25 - 50           | `bullet_heavy`    | 1                |
| 50 - 100          | `spitter_tier_3`  | 1                |
| 100 - 200         | `bullet`          | 3                |
| 200 - 400         | `bullet_heavy`    | 3                |
| 400 - 800         | `spitter_tier_3`  | 3                |
| 800 - 1600        | `spitter_tier_3`  | 3                |
| 1600 - 3200       | `bullet`          | 6                |
| 3200 - 6400       | `bullet_heavy`    | 6                |
| 6400+             | `spitter_tier_3`  | 6                |

*Note: The table above summarizes the projectile selection logic. The script uses a series of `if/elseif` statements to determine the projectile and count.*

## Code Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")

-- Configuration variables
local range = 200
local projectile_velocity_min = 570
local projectile_velocity_max = 630
local scatter = 0.15

-- Get entity information
local entity_id = GetUpdatedEntityID()
local root_id = EntityGetRootEntity(entity_id)
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Locate nearest enemy
local enemy, enemy_x, enemy_y
local min_dist = 9999
for _,id in pairs(EntityGetInRadiusWithTag(pos_x, pos_y, range, "mortal")) do
	-- Check if target is a valid enemy
	if (EntityGetComponent(id, "GenomeDataComponent") ~= nil) and (EntityGetHerdRelation(root_id, id) < 40) and (IsPlayer(root_id) ~= IsPlayer(id)) then
		local x, y = EntityGetFirstHitboxCenter( id )
		local dist = get_distance(pos_x, pos_y, x, y)
		if dist < min_dist then
			min_dist = dist
			enemy = id
			enemy_x = x
			enemy_y = y
		end
	end
end

-- If no enemy found, exit
if not enemy then return end

-- Check line of sight
if RaytraceSurfacesAndLiquiform(pos_x, pos_y, enemy_x, enemy_y) then return end

-- Calculate direction to enemy
local vel_x, vel_y = vec_sub(enemy_x, enemy_y, pos_x, pos_y)
vel_x,vel_y = vec_normalize(vel_x, vel_y)

-- Determine projectile type and count based on lost HP
local projectile = "light_bullet"
local count = 1
if IsPlayer(root_id) then
	component_read( EntityGetFirstComponent( root_id, "DamageModelComponent" ), { max_hp = 0, hp = 0 }, function(comp)
		local lost_hp = (comp.max_hp - comp.hp) * 25
		if lost_hp >= 6400 then
			projectile = "spitter_tier_3"
			count = 6
		elseif lost_hp >= 3200 then
			projectile = "bullet_heavy"
			count = 6
		elseif lost_hp >= 1600 then
			projectile = "bullet"
			count = 6
		elseif lost_hp >= 800 then
			projectile = "spitter_tier_3"
			count = 3
		elseif lost_hp >= 400 then
			projectile = "bullet_heavy"
			count = 3
		elseif lost_hp >= 200 then
			projectile = "bullet"
			count = 3
		elseif lost_hp >= 100 then
			projectile = "spitter_tier_3"
		elseif lost_hp >= 50 then
			projectile = "bullet_heavy"
		elseif lost_hp >= 25 then
			projectile = "bullet"
		end
	end)
end

-- Fire projectiles
SetRandomSeed(pos_x + GameGetFrameNum(), pos_y)
for i=1,count do
	-- Apply scatter to projectile direction
	local vx,vy = vec_rotate(vel_x,vel_y, rand(-scatter, scatter))
	scatter = scatter + 0.05 -- Increase scatter for subsequent shots

	-- Apply velocity and shoot
	vx,vy = vec_mult(vx,vy, rand(projectile_velocity_min, projectile_velocity_max))
	local eid = shoot_projectile( root_id, "data/entities/projectiles/deck/".. projectile .. ".xml", pos_x, pos_y, vx, vy)
end

-- Set random delay for execution
local comp_id = GetUpdatedComponentID()
if (comp_id ~= 0) then
	ComponentSetValue(comp_id, "execute_every_n_frame", 24 + Random(2))
end
```