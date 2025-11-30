---
title: Safe Haven Spawner
category: scripts
---

# Safe Haven Spawner

This script governs the creation and behavior of a "Safe Haven" entity, triggered by a thrown object. It handles the visual buildup, sound effects, the spawning of the Safe Haven building itself, healing projectiles, and various decorative props.

## Core Functionality

The script operates based on a timer relative to when the associated entity was thrown.

### Key Timings:

*   **`time_buildup_start`**: The initial delay before the visual buildup begins (120 frames).
*   **`time_spawn`**: The total delay from the throw until the Safe Haven fully spawns (100 frames after buildup starts).

### Event Triggers:

1.  **Buildup Phase**:
    *   Triggered when `GameGetFrameNum()` equals `throw_time + time_buildup_start`.
    *   Spawns a visual buildup particle effect (`safe_haven_buildup.xml`).
    *   Enables components tagged with `"enabled_before_spawn"`.
    *   Plays a "crumbling earth" sound effect.

2.  **Spawn Phase**:
    *   Triggered when `GameGetFrameNum()` equals `throw_time + time_spawn`.
    *   Plays a "heart full HP" sound effect.
    *   Spawns the main `safe_haven_building.xml`.
    *   Spawns healing projectiles.
    *   Spawns various decorative props.
    *   Destroys the spawner entity (`EntityKill(entity_id)`).

## Healing Projectile Generation

The script calculates the number and healing power of projectiles based on the player's current HP.

### Healing Calculation:

*   **Maximum Healing**: Projectiles can heal up to 60% of the player's maximum HP.
*   **Projectile Count**: The number of projectiles is determined by the available healing amount, with a cap of 20 shots for performance.
*   **Healing Per Projectile**: The total healing is divided equally among the spawned projectiles.

### Projectile Spawning:

*   A loop iterates `projectile_count` times.
*   Each projectile is spawned at a slightly randomized position near the Safe Haven.
*   The `ProjectileComponent` of each spawned projectile is modified to set its `damage_by_type` to "healing" with the calculated `hp` value.

## Prop Spawning

Several decorative and functional props are spawned around the Safe Haven.

### Key Props:

*   `physics/lantern_small.xml`
*   `furniture_bed.xml`
*   `furniture_wood_table.xml`
*   `physics_box_explosive.xml`

## Variables and Components

*   **`entity_id`**: The unique identifier for the current entity.
*   **`pos_x`, `pos_y`**: The world coordinates of the entity.
*   **`t`**: The current game frame number.
*   **`comp`**: A temporary variable for storing component data.
*   **`throw_time`**: An integer value stored in a `VariableStorageComponent` indicating when the entity was thrown.
*   **`storage_comp`**: A `VariableStorageComponent` used to retrieve the player's HP.
*   **`hp`**: The player's current HP, used to determine healing power.
*   **`projectile_count`**: The calculated number of healing projectiles to spawn.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local time_buildup_start = 120
local time_spawn = time_buildup_start + 100

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
local t = GameGetFrameNum()
local comp = get_variable_storage_component(entity_id, "throw_time")
local throw_time = ComponentGetValue2(comp, "value_int")

if throw_time < 0 then return end -- not thrown yet

if t == throw_time + time_buildup_start then
	-- buildup
	local e = EntityLoad("data/entities/particles/image_emitters/safe_haven_buildup.xml", pos_x, pos_y)
	EntityAddChild(entity_id, e)
	EntitySetComponentsWithTagEnabled(entity_id, "enabled_before_spawn", true)
	GamePlaySound( "data/audio/Desktop/projectiles.snd", "player_projectiles/crumbling_earth/create", pos_x, pos_y )
elseif t == throw_time + time_spawn then
	-- spawn safe haven
	GamePlaySound( "data/audio/Desktop/event_cues.bank", "event_cues/heart_fullhp/create", pos_x, pos_y )
	EntityLoad("data/entities/buildings/safe_haven_building.xml", pos_x, pos_y)
	
	-- spawn healing projectiles
	local storage_comp = get_variable_storage_component(entity_id, "player_hp")
	local hp = ComponentGetValue2(storage_comp, "value_float") * 0.6 -- max 60% healing
	local projectile_count = math.floor(math.min(20, hp * 3)) -- limit shots for performance reasons
	--print("total heal: " .. hp .. ". projectile amount " .. projectile_count)
	hp = hp / projectile_count -- hp per shot
	--print("heal per projectile: " .. hp)
	for i=1,projectile_count do
		local x = pos_x + ProceduralRandom(pos_x, pos_y - i, -10, 10)
		local y = pos_y + ProceduralRandom(pos_x + i, pos_y * 0.63, -8, 8) - 10
		local e = EntityLoad("data/entities/projectiles/healshot_safe_haven.xml", x, y)
		-- scale healing power of shots
		comp = EntityGetFirstComponent(e, "ProjectileComponent")
		ComponentObjectSetValue2(comp, "damage_by_type", "healing", -hp)
	end

	-- props
	EntityLoad("data/entities/props/physics/lantern_small.xml", pos_x - 1, pos_y - 32)
	EntityLoad("data/entities/props/furniture_bed.xml", pos_x - 36, pos_y - 8)
	EntityLoad("data/entities/props/furniture_wood_table.xml", pos_x + 41, pos_y - 8)
	EntityLoad("data/entities/props/physics_box_explosive.xml", pos_x + 46, pos_y - 12)
	
	-- cleanup
	EntityKill(entity_id)
end
```