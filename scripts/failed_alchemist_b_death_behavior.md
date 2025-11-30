---
title: Failed Alchemist B Death Behavior
category: scripts
---

# Failed Alchemist B Death Behavior

This script defines the behavior of the "Failed Alchemist B" entity when it dies.

## Core Functionality

The primary function `death` is triggered when the entity is destroyed.

### Key Actions

*   **Self-Destruction:** The entity is marked for removal.
*   **Orb Spawning:** Upon death, the entity spawns a `failed_alchemist_orb.xml` entity at its current position. This suggests a visual or functional consequence of the alchemist's demise.

### Function Signature

```lua
function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
```

*   `damage_type_bit_field`: An integer representing the type of damage that caused the death.
*   `damage_message`: A string containing a message related to the damage.
*   `entity_thats_responsible`: The entity ID of the entity that inflicted the damage.
*   `drop_items`: A boolean indicating whether items should be dropped upon death.

### Internal Logic

```lua
local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- do some kind of an effect? throw some particles into the air?
EntityLoad( "data/entities/buildings/failed_alchemist_orb.xml", pos_x, pos_y )
```

This snippet retrieves the entity's ID and its world coordinates. It then uses `EntityLoad` to instantiate the `failed_alchemist_orb.xml` entity at the death location. The commented-out line suggests potential for particle effects, which are not currently implemented in this specific script.