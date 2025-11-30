---
title: Laser Emitter Start Script
category: scripts
---

---

# Laser Emitter Start Script

This script is designed to be attached to an entity that has a `LaserEmitterComponent`. Its primary function is to immediately activate the laser emission when the entity is spawned or updated.

## Purpose

The script ensures that any `LaserEmitterComponent` attached to the entity begins emitting a laser upon the entity's activation.

## Key Components

### LaserEmitterComponent

This is the core component that this script interacts with. The script specifically targets the `is_emitting` property of this component.

## Functionality

The script performs the following actions:

1.  **Get Entity ID:** It retrieves the unique identifier for the current entity being processed.
2.  **Find Laser Emitter Components:** It searches for all attached `LaserEmitterComponent` instances on the entity.
3.  **Activate Emission:** For each found `LaserEmitterComponent`, it sets the `is_emitting` property to `true`, thereby starting the laser.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()

local comps = EntityGetComponent( entity_id, "LaserEmitterComponent" )
if ( comps ~= nil ) then
	for i,comp in ipairs( comps ) do
		ComponentSetValue2( comp, "is_emitting", true )
	end
end
```