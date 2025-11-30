---
title: Platform Disable Magic
category: scripts
---

---

# Platform Disable Magic

This script controls the behavior of a magic entity that can disable platforms. It checks for the presence of an "evil_eye" entity within a radius. If no "evil_eye" is found, it disables associated "magic_eye" components and kills child entities. If an "evil_eye" is found, it enables "magic_eye" components and spawns a platform collision entity.

## Core Logic

The script's primary function is to conditionally enable or disable platform entities based on the proximity of an "evil_eye" entity.

### Detection Mechanism

- **Radius Check:** The script scans for entities with the tag "evil_eye" within a 200-unit radius of the magic entity.
- **Light Component Check:** It specifically looks for "evil_eye" entities that possess a `LightComponent`. This implies that only "evil_eye" entities emitting light are considered for disabling platforms.

### Platform Disabling (No Evil Eye Found)

When no "evil_eye" entity with a `LightComponent` is detected:

- **Component Disabling:** The script disables components tagged with "magic_eye" on the magic entity itself.
- **Child Entity Cleanup:** It iterates through all child entities of the magic entity and destroys them. This is likely to remove any visual or functional elements associated with the platform when it's disabled.

### Platform Enabling (Evil Eye Found)

When an "evil_eye" entity with a `LightComponent` is detected:

- **Component Enabling:** The script enables components tagged with "magic_eye" on the magic entity.
- **Platform Spawning:** It loads and spawns a `platform_wide_collision.xml` entity at the magic entity's position.
- **Parenting:** The newly spawned platform collision entity is added as a child to the magic entity.

## Key Attributes and Components

While the script doesn't directly define components, it interacts with entities that possess them. The following are implied or directly referenced:

- **`ParticleEmitterComponent`:** The script checks for the presence of this component on the magic entity to determine its state.
- **`LightComponent`:** Used on "evil_eye" entities to determine their active status.
- **`magic_eye` Tag:** Components tagged with "magic_eye" on the magic entity are toggled by the script.
- **`evil_eye` Tag:** Used to identify the entities that trigger platform disabling.

## Entity Interactions

The script interacts with the following entity types:

- **Magic Entity:** The entity running this script.
- **`evil_eye` Entities:** Entities that, when present and emitting light, prevent platform disabling.
- **`platform_wide_collision.xml`:** A prefab entity that is spawned to create the platform.

## Code Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Check for nearby 'evil_eye' entities with a LightComponent
local test = EntityGetInRadiusWithTag( x, y, 200, "evil_eye" )
local found = false

for i,v in ipairs( test ) do
	local c = EntityGetComponent( v, "LightComponent" )
	if ( c ~= nil ) then
		found = true
		break
	end
end

-- If no 'evil_eye' is found
if ( found == false ) then
	local c_ = EntityGetComponent( entity_id, "ParticleEmitterComponent" )
	if ( c_ ~= nil ) then
		-- Disable magic_eye components and kill child entities
		EntitySetComponentsWithTagEnabled( entity_id, "magic_eye", false )
		local c = EntityGetAllChildren( entity_id )
		if ( c ~= nil ) then
			for a,b in ipairs( c ) do
				EntityKill( b )
			end
		end
	end
else -- If an 'evil_eye' is found
	local c = EntityGetComponent( entity_id, "ParticleEmitterComponent" )
	if ( c == nil ) then
		-- Enable magic_eye components and spawn platform collision
		EntitySetComponentsWithTagEnabled( entity_id, "magic_eye", true )
		local eid = EntityLoad( "data/entities/misc/platform_wide_collision.xml", x, y )
		EntityAddChild( entity_id, eid )
	end
end
```