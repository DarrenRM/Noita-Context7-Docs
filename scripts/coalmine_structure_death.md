---
title: Coalmine Structure Death
category: scripts
---

# Coalmine Structure Death

This script defines the behavior when a "coalmine structure" entity is destroyed.

## `death` Function

This function is called when the entity associated with this script receives damage and is destroyed.

### Parameters

*   `damage_type_bit_field`: An integer representing the type of damage received.
*   `damage_message`: A string containing a message related to the damage.
*   `entity_thats_responsible`: The entity that inflicted the damage.
*   `drop_items`: A boolean indicating whether items should be dropped upon death.

### Core Logic

The primary action of this script is to spawn a `loose_ground.xml` entity at the position of the destroyed structure.

```lua
function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	local entity_id		= GetUpdatedEntityID()
	local pos_x, pos_y	= EntityGetTransform( entity_id )

	EntityLoad( "data/entities/misc/loose_ground.xml", pos_x, pos_y )
end
```