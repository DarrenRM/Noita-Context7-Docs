---
title: Twitchy Shot Status Effect
category: scripts/status_effects
---

# Twitchy Shot Status Effect

This script defines a status effect that modifies projectile behavior, specifically enabling friendly fire and allowing projectiles to collide with their shooter shortly after being fired.

## Core Functionality

The `shot` function is the primary logic for this status effect. It's designed to be applied to projectiles.

### Key Modifications

*   **Friendly Fire:** The projectile is set to be able to damage its owner.
*   **Collision with Shooter:** The projectile will collide with the entity that fired it for a short duration (6 frames).
*   **Tagging:** The projectile is tagged with `"friendly_fire_enabled"` to ensure the effect is consistently applied.

### Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

function shot( entity_id )
	-- Modifies the ProjectileComponent of the entity.
	edit_component( entity_id, "ProjectileComponent", function(comp,vars)
		-- Enables friendly fire for the projectile.
		ComponentSetValue2( comp, "friendly_fire", true )
		-- Sets the number of frames the projectile will collide with its shooter.
		ComponentSetValue2( comp, "collide_with_shooter_frames", 6 )
	end)
	
	-- Adds a tag to ensure friendly fire is consistently enabled.
	if ( EntityHasTag( entity_id, "friendly_fire_enabled" ) == false ) then
		EntityAddTag( entity_id, "friendly_fire_enabled" )
	end
end
```