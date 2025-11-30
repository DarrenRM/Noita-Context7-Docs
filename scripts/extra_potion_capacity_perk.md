---
title: Extra Potion Capacity Perk
category: scripts
---

# Extra Potion Capacity Perk

This script modifies the capacity of potion barrels when the "Extra Potion Capacity" perk is active.

## Functionality

The script iterates through all entities tagged as "potion". For each potion entity that doesn't already have the "extra_potion_capacity" tag:

1.  It retrieves the `MaterialSuckerComponent`.
2.  If the component exists, it sets the `barrel_size` property to the value of the global variable `EXTRA_POTION_CAPACITY_LEVEL`.
3.  It adds the "extra_potion_capacity" tag to the potion entity to prevent re-processing.

## Key Attributes/Elements

*   **`EXTRA_POTION_CAPACITY_LEVEL`**: A global variable that defines the new `barrel_size` for potions. Defaults to "1000" if not found.
*   **`EntityGetWithTag("potion")`**: Retrieves all entities with the "potion" tag.
*   **`EntityHasTag(target_id, "extra_potion_capacity")`**: Checks if a potion entity has already been modified by this perk.
*   **`EntityGetFirstComponentIncludingDisabled(target_id, "MaterialSuckerComponent")`**: Gets the `MaterialSuckerComponent` from a potion entity.
*   **`ComponentSetValue(comp, "barrel_size", total_capacity)`**: Sets the `barrel_size` property of the `MaterialSuckerComponent`.
*   **`EntityAddTag(target_id, "extra_potion_capacity")`**: Marks a potion entity as having its capacity modified.

## Example Usage (Conceptual)

To increase the potion capacity, you would typically modify the `EXTRA_POTION_CAPACITY_LEVEL` global value. For instance, in another script or configuration file:

```lua
-- Example of setting the global value
GlobalsSetValue( "EXTRA_POTION_CAPACITY_LEVEL", "2000" )
```

This would make all potions affected by this perk have a `barrel_size` of 2000.