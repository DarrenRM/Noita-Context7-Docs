---
title: Projectile Caster Script
category: scripts
---

---

# Projectile Caster Script

This script defines the behavior for projectiles that are cast by entities. It primarily focuses on positioning the projectile at the caster's location.

## Key Functionality

*   **Entity Identification:** Retrieves the `entity_id` of the projectile being processed.
*   **Positioning:** Obtains the current position (`pos_x`, `pos_y`) of the projectile.
*   **Owner Identification:** Determines the `owner_id` of the projectile by accessing its `ProjectileComponent` and the `mWhoShot` attribute.
*   **Caster Positioning:** If an owner is identified, it finds the owner's hitbox center (`tx`, `ty`).
*   **Projectile Relocation:** Sets the projectile's transform to match the owner's hitbox center, effectively casting the projectile from the owner's position.

## Core Lua Snippets

```lua
local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
local owner_id = 0

local comp = EntityGetFirstComponent( entity_id, "ProjectileComponent" )
if ( comp ~= nil ) then
	owner_id = ComponentGetValue2( comp, "mWhoShot" )
end

if ( owner_id ~= nil ) and ( owner_id ~= NULL_ENTITY ) then
	local tx, ty = EntityGetFirstHitboxCenter( owner_id )
	
	EntitySetTransform( entity_id, tx, ty )
end
```

## Key Components and Attributes

*   **`ProjectileComponent`**: This component is essential for identifying the projectile and its owner.
    *   **`mWhoShot`**: An attribute within `ProjectileComponent` that stores the `entity_id` of the entity that shot the projectile.
*   **`GetUpdatedEntityID()`**: A global function to get the ID of the entity currently being updated.
*   **`EntityGetTransform( entity_id )`**: Retrieves the transform (position) of an entity.
*   **`EntitySetTransform( entity_id, x, y )`**: Sets the transform (position) of an entity.
*   **`EntityGetFirstHitboxCenter( entity_id )`**: Returns the center coordinates of an entity's hitbox.
*   **`NULL_ENTITY`**: A constant representing an invalid or non-existent entity.