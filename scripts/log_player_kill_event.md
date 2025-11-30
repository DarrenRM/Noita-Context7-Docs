---
title: Log Player Kill Event
category: scripts
---

# Log Player Kill Event

This script defines a function to log when a player is killed by an entity.

## `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called when an entity dies. It specifically logs player kills.

### Parameters

*   `damage_type_bit_field`: A bitfield representing the type of damage that caused the death.
*   `damage_message`: A string describing the damage.
*   `entity_thats_responsible`: The entity ID of the entity that caused the death.
*   `drop_items`: A boolean indicating whether items should be dropped.

### Core Functionality

*   **`StatsLogPlayerKill( entity_id )`**: This is the primary function called within `death`. It logs the event of a player being killed, using the `entity_id` of the entity that died. This is crucial for tracking player deaths in game statistics.