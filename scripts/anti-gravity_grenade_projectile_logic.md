---
title: Anti-Gravity Grenade Projectile Logic
category: scripts
---

---

# Anti-Gravity Grenade Projectile Logic

This script defines the behavior of the Anti-Gravity Grenade projectile in Noita. It dynamically adjusts the projectile's gravity based on the vertical position of its owner.

## Key Functionality

The core logic of this script is to modify the `gravity_y` component of the projectile.

### Gravity Adjustment

- **Condition:** The script checks if the projectile has a `ProjectileComponent` and a `VelocityComponent`.
- **Owner Check:** It then verifies if the projectile has a valid owner (`mWhoShot`).
- **Vertical Alignment:**
    - If the owner's `y` position is *above* the projectile's `y` position, the projectile's `gravity_y` is set to `600` (pulling it downwards).
    - If the owner's `y` position is *below* the projectile's `y` position, the projectile's `gravity_y` is set to `-600` (pushing it upwards).

## Relevant Components

The script interacts with the following Noita components:

- **`ProjectileComponent`**: Used to identify the projectile and retrieve its owner.
- **`VelocityComponent`**: Used to modify the projectile's gravity.

## Lua Snippets

```lua
-- Retrieve the projectile's entity ID
local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Get the ProjectileComponent and VelocityComponent
local comp = EntityGetFirstComponent( entity_id, "ProjectileComponent" )
local comp2 = EntityGetFirstComponent( entity_id, "VelocityComponent" )

if ( comp ~= nil ) and ( comp2 ~= nil ) then
	-- Get the ID of the entity that shot the projectile
	local owner_id = ComponentGetValue2( comp, "mWhoShot" )
	
	if ( owner_id ~= nil ) and ( owner_id ~= NULL_ENTITY ) then
		-- Get the owner's transform
		local px, py = EntityGetTransform( owner_id )
		
		if ( px ~= nil ) and ( py ~= nil ) then
			-- Adjust gravity based on owner's vertical position
			if ( py > y ) then
				ComponentSetValue2( comp2, "gravity_y", 600 ) -- Owner is above, pull down
			elseif ( py < y ) then
				ComponentSetValue2( comp2, "gravity_y", -600 ) -- Owner is below, push up
			end
		end
	end
end
```