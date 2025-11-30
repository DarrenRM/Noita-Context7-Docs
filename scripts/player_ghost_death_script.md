---
title: Player Ghost Death Script
category: scripts
---

# Player Ghost Death Script

This script defines the behavior when a player's ghost entity dies.

## Function: `death`

This function is called when the player ghost entity is destroyed.

### Parameters:

*   `damage_type_bit_field` (number): A bitfield representing the type of damage that caused the death.
*   `damage_message` (string): A message describing the damage.
*   `entity_thats_responsible` (EntityID): The ID of the entity that caused the death.
*   `drop_items` (boolean): Whether items should be dropped upon death.

### Core Logic:

*   **`StatsLogPlayerKill( entity_id )`**: Logs the player's death for statistical purposes. The `entity_id` is retrieved using `GetUpdatedEntityID()`.