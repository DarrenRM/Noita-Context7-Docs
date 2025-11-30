---
title: Maggot Tiny Death Behavior
category: entities
---

# Maggot Tiny Death Behavior

This Lua script defines the behavior of the "Maggot Tiny" entity when it dies. It handles item drops and game state changes.

## Key Functions

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function is called when the Maggot Tiny entity is killed.

*   **`damage_type_bit_field`**: A bitfield representing the type of damage that killed the entity.
*   **`damage_message`**: A string message associated with the damage.
*   **`entity_thats_responsible`**: The ID of the entity that caused the death.
*   **`drop_items`**: A boolean indicating whether items should be dropped.

## Core Logic

1.  **Self-Identification**:
    *   `local entity_id = GetUpdatedEntityID()`: Retrieves the unique ID of the entity executing this script.
    *   `local pos_x, pos_y = EntityGetTransform( entity_id )`: Gets the current position of the entity.

2.  **Item Spawning**:
    *   The script spawns several items at slightly offset positions around the entity's death location. These include:
        *   `data/entities/items/pickup/heart_better.xml`
        *   `data/entities/items/pickup/heart_fullhp.xml`
        *   `data/entities/items/wand_unshuffle_06.xml`
        *   `data/entities/items/wand_unshuffle_10.xml`

3.  **Game State Flags**:
    *   `GameAddFlagRun( "miniboss_maggot" )`: Adds a temporary flag for the current run, likely indicating a miniboss encounter.
    *   `AddFlagPersistent( "miniboss_maggot" )`: Adds a persistent flag for the current save file.
    *   `AddFlagPersistent( "card_unlocked_maggot" )`: Adds a persistent flag, potentially unlocking a related card or feature.

## Notes

*   The commented-out lines `StatsLogPlayerKill( entity_id )` and `EntityKill( entity_id )` suggest that the default entity killing behavior might be overridden or handled elsewhere.
*   The specific items dropped are fixed and not dependent on the `drop_items` parameter or damage type.