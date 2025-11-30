---
title: Boss Meat Death Handler
category: entities
---

# Boss Meat Death Handler

This script defines the behavior when the "Boss Meat" entity dies in Noita. It handles persistent flags, global variable updates, item drops, and disabling a specific healing effect.

## Key Functions

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called when the Boss Meat entity is defeated.

*   **`damage_type_bit_field`**: (Not used in this function)
*   **`damage_message`**: (Not used in this function)
*   **`entity_thats_responsible`**: (Not used in this function)
*   **`drop_items`**: (Not used in this function)

## Core Logic

1.  **Self-Identification**:
    *   `local entity_id = GetUpdatedEntityID()`: Retrieves the unique ID of the entity executing this script.
    *   `local pos_x, pos_y = EntityGetTransform( entity_id )`: Gets the current position of the entity.

2.  **Persistent State Update**:
    *   `AddFlagPersistent( "miniboss_meat" )`: Sets a persistent flag indicating that the "miniboss_meat" has been defeated. This flag can be checked by other game systems.
    *   `GlobalsSetValue( "BOSS_MEAT_DEAD", "1" )`: Updates a global game variable to mark the Boss Meat as dead.

3.  **Item Drop**:
    *   `EntityLoad( "data/entities/items/wands/experimental/experimental_wand_4.xml", pos_x, pos_y - 12 )`: Spawns an "experimental\_wand\_4" item at the Boss Meat's location (slightly above it).

4.  **Healing Effect Management**:
    *   The script searches for entities with the tag `"no_heal_in_meat_biome"`.
    *   If such entities are found:
        *   It iterates through them and disables the component tagged `"effect_no_heal_in_meat_biome"`. This likely means that entities previously prevented from healing in the meat biome will now be able to heal.
        *   `GamePrintImportant( "$log_boss_meat_death", "$logdesc_boss_meat_death" )`: Displays an important in-game message to the player, likely indicating the Boss Meat's demise and potentially the change in healing mechanics.