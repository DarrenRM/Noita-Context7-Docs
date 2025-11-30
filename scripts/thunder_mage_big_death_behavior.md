---
title: Thunder Mage Big Death Behavior
category: scripts
---

# Thunder Mage Big Death Behavior

This script defines the behavior of a "big death" event for a Thunder Mage entity in Noita. When the entity dies, it triggers a specific action.

## Core Functionality

The primary function is `death()`, which is called when the entity is destroyed.

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function handles the death event.

*   **`entity_id`**: The ID of the entity that is dying.
*   **`pos_x`, `pos_y`**: The current position of the dying entity.

## Key Actions

When the Thunder Mage dies, the following action is performed:

*   **Projectile Spawn**: A `thunderball.xml` projectile is shot from the entity's position.

```lua
function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )

	-- Shoots a thunderball projectile from the entity's location upon death.
	shoot_projectile( entity_id, "data/entities/projectiles/thunderball.xml", pos_x, pos_y, 0, 0 )
end
```