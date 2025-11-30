---
title: Friend Death Script
category: scripts
---

---

# Friend Death Script

This script defines the behavior when a "friend" entity dies in Noita. It primarily handles incrementing a global kill counter and potentially triggering a persistent flag based on that count.

## Key Functionality

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called when the entity associated with this script dies.

*   **`damage_type_bit_field`**: A bitfield representing the type of damage that caused the death.
*   **`damage_message`**: A string describing the damage message.
*   **`entity_thats_responsible`**: The ID of the entity that caused the death.
*   **`drop_items`**: A boolean indicating whether items should be dropped upon death.

## Global State Management

### `ULTIMATE_KILLER_KILLS`

*   This global variable tracks the number of kills attributed to a specific entity or condition (likely related to the "Ultimate Killer").
*   The script retrieves its current value using `GlobalsGetValue`.
*   If the kill count reaches or exceeds 9, the persistent flag `"final_secret_orb3"` is added.

## Example Usage (Conceptual)

This script would be attached to an entity that acts as a "friend" or a target that contributes to the "Ultimate Killer" kill count. When this entity is destroyed, the `death` function is invoked, potentially updating the global kill counter and unlocking a secret if the threshold is met.

```lua
-- Conceptual attachment to an entity
-- entity.xml
-- <entity name="my_friend_entity">
--     <components>
--         <death_script name="data/scripts/animals/friend_death.lua" />
--     </components>
-- </entity>
```