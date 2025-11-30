---
title: Monk Hand Shooting Logic
category: scripts
---

# Monk Hand Shooting Logic

This script defines the behavior for a "Monk Hand" entity in Noita, specifically its projectile-firing mechanism. It targets the nearest mortal enemy within a defined range, checks for line-of-sight, and then shoots a projectile.

## Key Attributes and Behavior

### Targeting and Range
- **`range`**: Defines the maximum distance (in pixels) the Monk Hand will search for enemies.
  - Default: `200`

### Projectile Properties
- **`projectile_velocity`**: The speed at which the fired projectile travels.
  - Default: `20`
- **`scatter`**: Controls the randomness or spread of the projectile's trajectory. A higher value means more scatter.
  - Default: `0.2`
- **`shoot_projectile`**: The function used to instantiate and launch a projectile.
  - **Projectile XML**: `data/entities/projectiles/orb_green_accelerating.xml`

### Enemy Detection
- The script iterates through entities within the `range` that have the `"mortal"` tag.
- It filters for valid enemies by checking for a `GenomeDataComponent` and ensuring the target is not part of the same "herd" (relation value less than 40).
- The closest valid enemy is selected as the target.

### Line of Sight (LOS) Check
- **`RaytraceSurfacesAndLiquiform`**: Used to determine if there is an unobstructed path between the Monk Hand and the target enemy.
- If LOS is blocked, the hand will open (indicating it cannot shoot).

### Animation and State Control
- **`SpriteComponent`**: The script interacts with the `SpriteComponent` to control the hand's animation state.
  - **`rect_animation`**:
    - `"open"`: The hand is open, indicating it's not ready to shoot or cannot see an enemy.
    - `"close"`: The hand closes, preparing to fire.
- The hand opens if no enemy is visible or if LOS is blocked.
- The hand closes to prepare for shooting when an enemy is visible and LOS is clear.

### Shooting Mechanics
- **Direction Calculation**: The script calculates the vector towards the enemy and normalizes it.
- **Offsetting Shot Position**: The firing position is slightly offset in the direction of the enemy to prevent the projectile from colliding with the hand itself.
- **Applying Scatter**: Random rotation is applied to the projectile's velocity vector based on the `scatter` value.
- **Projectile Launch**: The `shoot_projectile` function is called with the calculated position, velocity, and projectile type.

### Firing Delay
- **`ComponentSetValue(GetUpdatedComponentID(), "execute_every_n_frame", 55 + Random(10))`**: After firing, the script introduces a random delay before it can fire again. This prevents multiple hands from firing simultaneously and creates a more natural rhythm.
  - The delay is between 55 and 65 frames.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local range = 200
local projectile_velocity = 20
local scatter = 0.2

local entity_id = GetUpdatedEntityID()
local root_id = EntityGetRootEntity(entity_id)
local pos_x, pos_y = EntityGetFirstHitboxCenter( entity_id )

-- locate nearest enemy
local enemy, enemy_x, enemy_y
local min_dist = 9999
for _,id in pairs(EntityGetInRadiusWithTag(pos_x, pos_y, range, "mortal")) do
	-- is target a valid enemy
	if EntityGetComponent(id, "GenomeDataComponent") ~= nil and EntityGetHerdRelation(root_id, id) < 40 then
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

-- check los
local can_shoot = false
if enemy then can_shoot = not RaytraceSurfacesAndLiquiform(pos_x, pos_y, enemy_x, enemy_y) end

-- hand/shooting state & animation control
edit_component2( entity_id, "SpriteComponent", function(comp,vars)
	-- if enemy is not visible then open hand
	local hand_check = ComponentGetValue2( comp, "rect_animation" )
	local hand_open = false
	
	if ( hand_check ~= nil ) and ( hand_check == "open" ) then
		hand_open = true
	end
	
	if not can_shoot then
		if not hand_open then
			ComponentSetValue2( comp, "rect_animation", "open")
			--EntitySetComponentsWithTagEnabled( entity_id, "enabled_when_attacking", false )
		end
		return
	end

	-- prepare to shoot
	if hand_open then
		ComponentSetValue2( comp, "rect_animation", "close")
		--EntitySetComponentsWithTagEnabled( entity_id, "enabled_when_attacking", true )
		can_shoot = false
		return
	end
end)

if not can_shoot then return end

-- direction
local vel_x, vel_y = vec_sub(enemy_x, enemy_y, pos_x, pos_y)
vel_x,vel_y = vec_normalize(vel_x, vel_y)

-- offset to shoot direction to avoid colliding with hand
pos_x = pos_x + vel_x * 8
pos_y = pos_y + vel_y * 8

-- scatter
SetRandomSeed(pos_x + GameGetFrameNum(), pos_y)
vel_x,vel_y = vec_rotate(vel_x,vel_y, rand(-scatter, scatter))

-- apply velocity & shoot
vel_x,vel_y = vec_mult(vel_x,vel_y, projectile_velocity)
shoot_projectile( root_id, "data/entities/projectiles/orb_green_accelerating.xml", pos_x, pos_y, vel_x, vel_y)
--EntityLoad("data/entities/particles/particle_explosion/main_swirly_green.xml", pos_x, pos_y)

-- delay randomly so that multiple hands shoot at different times
ComponentSetValue(GetUpdatedComponentID(), "execute_every_n_frame", 55 + Random(10))
```