---
title: Sentry Bot AI Behavior
category: scripts
---

---

# Sentry Bot AI Behavior

This script defines the ranged attack behavior for sentry-type enemies in Noita. It dynamically adjusts the projectile type and firing rate based on the presence of entities tagged as "sentry_target".

## Core Functionality

The script retrieves the `AnimalAIComponent` for the entity and checks for the existence of any entities with the tag "sentry_target".

### Attack Configuration

-   **If "sentry_target" entities are present:**
    -   The sentry will fire `machinegun_bullet_roboguard_big.xml` projectiles.
    -   The `attack_ranged_frames_between` is set to `20` (faster firing rate).
-   **If no "sentry_target" entities are present:**
    -   The sentry will fire `sentryshot.xml` projectiles.
    -   The `attack_ranged_frames_between` is set to `90` (slower firing rate).

## Key Components

-   `AnimalAIComponent`: This component manages the AI behavior of the entity, including its attack patterns.
-   `EntityGetWithTag("sentry_target")`: A function used to find all entities in the game world that have been assigned the "sentry_target" tag.

## Lua Script Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()

local comp = EntityGetFirstComponent( entity_id, "AnimalAIComponent" )

if ( comp ~= nil ) then
	local targets = EntityGetWithTag( "sentry_target" )
	
	if ( #targets > 0 ) then
		ComponentSetValue2( comp, "attack_ranged_entity_file", "data/entities/projectiles/machinegun_bullet_roboguard_big.xml" )
		ComponentSetValue2( comp, "attack_ranged_frames_between", 20 )
	else
		ComponentSetValue2( comp, "attack_ranged_entity_file", "data/entities/projectiles/sentryshot.xml" )
		ComponentSetValue2( comp, "attack_ranged_frames_between", 90 )
	end
end
```