---
title: Curse Stronger Projectile Initialization
category: scripts
---

# Curse Stronger Projectile Initialization

This script handles the initialization and stacking logic for the "Curse Stronger" effect, typically applied by projectiles. It ensures that the curse effect is applied correctly and that its duration and potency are updated if the effect is already active.

## Core Functionality

The script's primary goal is to manage the "effect_CURSE" tag and associated components on the player entity.

### Key Actions:

1.  **Check for Existing Curse:** It first checks if the player entity already possesses the "effect_CURSE" tag.
2.  **Apply New Curse:** If the tag is not present, it loads and attaches a `curse_stronger.xml` entity to the player and adds the "effect_CURSE" tag.
3.  **Update Existing Curse:** If the tag is present, it searches for the associated curse entity and updates its `LifetimeComponent` and `VariableStorageComponent` to extend its duration and increase its damage.
4.  **Self-Destruction:** The projectile entity that triggered this script is always killed upon completion of its logic.

## Script Logic Breakdown

The script uses `dofile_once` to include utility functions and then proceeds with the core logic.

### Initialization and Tagging

```lua
local entity_id = GetUpdatedEntityID()
local root_id = EntityGetRootEntity( entity_id )

local x,y = EntityGetTransform( root_id )
local curseflag = EntityHasTag( root_id, "effect_CURSE" )
```

*   `entity_id`: Gets the ID of the current projectile entity.
*   `root_id`: Retrieves the root entity of the projectile (usually the player).
*   `x, y`: Gets the player's current position.
*   `curseflag`: A boolean indicating if the player already has the "effect_CURSE" tag.

### Applying a New Curse

```lua
if ( curseflag == false ) then
	local eid = EntityLoad( "data/entities/misc/curse_stronger.xml", x, y )
	EntityAddChild( root_id, eid )
	EntityAddTag( root_id, "effect_CURSE" )
else
	-- Logic for updating existing curse
end
```

*   If `curseflag` is `false`, a new `curse_stronger.xml` entity is loaded at the player's position.
*   This new entity is added as a child to the player (`root_id`).
*   The "effect_CURSE" tag is added to the player.

### Updating an Existing Curse

```lua
	local c = EntityGetAllChildren( root_id )
	if ( c ~= nil ) then
		for i,v in ipairs( c ) do
			if EntityHasTag( v, "effect_CURSE" ) then
				local comp = EntityGetFirstComponent( v, "LifetimeComponent", "effect_curse_lifetime" )

				if ( comp ~= nil ) then
					ComponentSetValue2( comp, "creation_frame", GameGetFrameNum() )
					ComponentSetValue2( comp, "kill_frame", GameGetFrameNum() + 300 )

					comp = EntityGetFirstComponent( v, "VariableStorageComponent", "effect_curse_damage" )

					if ( comp ~= nil ) then
						local damage = ComponentGetValue2( comp, "value_float" )
						damage = damage + 0.08
						ComponentSetValue2( comp, "value_float", damage )
					end
				end

				break
			end
		end
	end
```

*   If `curseflag` is `true`, the script iterates through all children of the player entity.
*   It looks for a child entity that has the "effect_CURSE" tag.
*   **Lifetime Update:**
    *   It retrieves the `LifetimeComponent` (named "effect_curse_lifetime").
    *   `creation_frame` is set to the current game frame.
    *   `kill_frame` is extended by 300 frames from the current game frame.
*   **Damage Update:**
    *   It retrieves the `VariableStorageComponent` (named "effect_curse_damage").
    *   The `value_float` (damage) is increased by `0.08`.
    *   The updated damage value is set back into the component.
*   The loop breaks once the relevant curse entity is found and updated.

### Projectile Cleanup

```lua
EntityKill( entity_id )
```

*   Finally, the projectile entity that initiated this script is destroyed.