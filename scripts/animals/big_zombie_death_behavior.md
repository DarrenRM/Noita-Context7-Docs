---
title: Big Zombie Death Behavior
category: scripts/animals
---

# Big Zombie Death Behavior

This script defines the behavior of the "Big Zombie" entity when it dies.

## Core Functionality

The primary function `death` is triggered when the Big Zombie entity is destroyed. It handles the entity's demise by:

### Key Actions

*   **Spawning Torso:** Creates a `bigzombietorso.xml` entity at the zombie's current location.
*   **Spawning Head:** Creates a `bigzombiehead.xml` entity at the zombie's current location.

## Script Details

```lua
dofile_once("data/scripts/lib/utilities.lua")

function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	local x, y = EntityGetTransform( GetUpdatedEntityID() )
	EntityLoad( "data/entities/animals/bigzombietorso.xml", x, y )	
	EntityLoad( "data/entities/animals/bigzombiehead.xml",  x, y )
end
```

### Function Parameters

*   `damage_type_bit_field`: A bitfield indicating the type of damage that killed the entity.
*   `damage_message`: A string containing a message related to the damage.
*   `entity_thats_responsible`: The entity ID of the entity that dealt the killing blow.
*   `drop_items`: A boolean indicating whether items should be dropped upon death.

### Internal Logic

*   `GetUpdatedEntityID()`: Retrieves the ID of the entity that is currently being updated (in this case, the dying Big Zombie).
*   `EntityGetTransform()`: Gets the position (x, y coordinates) of the entity.
*   `EntityLoad()`: Spawns a new entity from an XML file at a specified location.