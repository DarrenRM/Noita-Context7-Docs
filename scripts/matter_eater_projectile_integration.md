---
title: Matter Eater Projectile Integration
category: scripts
---

---

# Matter Eater Projectile Integration

This script defines how the "Matter Eater" entity is spawned when a specific projectile is fired.

## Function: `shot`

This function is responsible for loading the Matter Eater entity into the game world.

### Parameters

*   `projectile_id`: The unique identifier of the projectile that triggered this event.

### Behavior

When called, this function executes `EntityLoadToEntity`, which spawns the `data/entities/misc/matter_eater.xml` entity. The new entity is attached to the provided `projectile_id`, meaning it will follow or be associated with the projectile that initiated its creation.

```lua
function shot( projectile_id )
	EntityLoadToEntity( "data/entities/misc/matter_eater.xml", projectile_id )
end
```