---
title: Big Zombie Head Death Behavior
category: scripts
---

# Big Zombie Head Death Behavior

This script defines the behavior of the "Big Zombie Head" entity when it dies in Noita.

## Key Functionality

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called when the Big Zombie Head entity is destroyed.

*   **`damage_type_bit_field`**: A bitfield representing the type of damage that killed the entity.
*   **`damage_message`**: A string describing the damage message.
*   **`entity_thats_responsible`**: The entity ID that caused the death.
*   **`drop_items`**: A boolean indicating whether items should be dropped.

### Core Action: Explosion

The primary action upon death is the creation of an explosion.

*   **`local x, y = EntityGetTransform( GetUpdatedEntityID() )`**: Retrieves the current position (x, y coordinates) of the entity that is being updated (in this case, the dying Big Zombie Head).
*   **`EntityLoad( "data/entities/projectiles/explosion.xml", x, y )`**: This is the crucial line that spawns an explosion entity at the Big Zombie Head's location. The explosion's behavior and appearance are defined in `data/entities/projectiles/explosion.xml`.

---