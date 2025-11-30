---
title: Leggy Feet Perk Drop on Death
category: scripts
---

---

# Leggy Feet Perk Drop on Death

This script defines the behavior when a specific entity dies, causing it to drop the "Leggy Feet" perk.

## Function: `death`

This function is called when the entity associated with this script is destroyed.

### Parameters:

*   `damage_type_bit_field`: An integer representing the type of damage that caused the death.
*   `damage_message`: A string describing the damage.
*   `entity_thats_responsible`: The entity that inflicted the damage.
*   `drop_items`: A boolean indicating whether items should be dropped.

### Core Logic:

1.  **Get Entity Information**: Retrieves the current entity ID and its position (`pos_x`, `pos_y`).
2.  **Spawn "Leggy Feet" Perk**: Calls `perk_spawn` to create the "LEGGY_FEET" perk at the entity's location.
3.  **Prevent Perk Removal**: If the perk was successfully spawned (`perk_id` is not `nil`):
    *   Adds a `VariableStorageComponent` to the spawned perk.
    *   Sets the `name` to `"perk_dont_remove_others"`.
    *   Sets the `value_bool` to `"1"`, which likely prevents this perk from being automatically removed by other game mechanics.