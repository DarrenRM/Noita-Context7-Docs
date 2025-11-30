---
title: Boss Limbs Spawn Logic
category: entities
---

# Boss Limbs Spawn Logic

This script defines the behavior when a boss limb entity is triggered, typically for spawning purposes.

## `collision_trigger()` Function

This function is executed when the entity associated with this script is triggered (e.g., by collision).

### Key Actions:

*   **Spawn Boss Limb:** Loads the main `boss_limbs.xml` entity at the current position.
*   **Spawn Particle Effect:** Loads a `magical_symbol_fast.xml` particle emitter at the current position, likely for visual feedback during spawning.
*   **Self-Destruct:** Removes the triggering entity using `EntityKill()`.

### Code:

```lua
function collision_trigger()
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )
	EntityLoad( "data/entities/animals/boss_limbs/boss_limbs.xml", pos_x, pos_y )
	EntityLoad( "data/entities/particles/image_emitters/magical_symbol_fast.xml", pos_x, pos_y )
	EntityKill( entity_id )
end
```