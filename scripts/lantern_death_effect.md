---
title: Lantern Death Effect
category: scripts
---

# Lantern Death Effect

This script defines the behavior for when a "lantern" entity dies. It triggers a particle effect at the entity's location.

## Function: `death`

This function is called when the entity associated with this script is destroyed.

### Parameters:

*   `damage_type_bit_field` (number): A bitfield representing the type of damage that caused the death.
*   `damage_message` (string): A message describing the damage.
*   `entity_thats_responsible` (entity): The entity that caused the death.
*   `drop_items` (boolean): Whether items should be dropped upon death.

### Behavior:

1.  Retrieves the current entity's ID.
2.  Gets the entity's position (`pos_x`, `pos_y`).
3.  Loads a particle effect entity (`data/entities/particles/lantern_death.xml`) at the entity's position.

### Example Usage (Internal):

This function is typically called internally by the game engine when an entity with this script attached is destroyed.

```lua
-- Example of how the game might call this function (not for direct modder use)
-- death( DAMAGE_TYPE_EXPLOSION, "Exploded", some_other_entity_id, true)
```