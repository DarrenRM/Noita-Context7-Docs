---
title: Mana From Kills Perk Effect
category: scripts
---

# Mana From Kills Perk Effect

This script defines the behavior for the "Mana From Kills" perk in Noita. When a player with this perk kills an enemy, it can trigger the spawning of mana-restoring effects.

## Core Functionality

The `death` function is the primary handler for this perk. It's called when an entity dies.

### Key Attributes & Logic

*   **`death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`**: The main function executed upon entity death.
    *   Retrieves the `entity_id` of the dying entity.
    *   Gets the position (`pos_x`, `pos_y`) of the dying entity.
    *   Initializes a random seed based on game frame and entity position.
    *   Retrieves the `player_id` associated with the "Mana From Kills" perk from a `VariableStorageComponent`. This component is expected to be attached to the entity that *owns* the perk.
    *   Reads the `PERK_PICKUP_COUNT` global variable, which determines how many mana effects to spawn.
    *   If a valid `player_id` is found and `pickup_count` is greater than 0, it proceeds to spawn effects.
    *   For each `pickup_count`, it loads and spawns `data/entities/misc/perks/mana_from_kills_effect.xml` at the death location.
    *   The spawned effect entity is then attached as a child to the `player_id` entity, ensuring it's managed by the player.

## Relevant Entities

*   **`data/entities/misc/perks/mana_from_kills_effect.xml`**: This is the entity that is spawned when the perk's conditions are met. It's responsible for the visual and functional aspect of restoring mana.

## Global Variables

*   **`PERK_PICKUP_COUNT`**: A global variable that stores the number of mana effects to spawn per kill. This value is likely set by the perk's acquisition logic.

## Components Used

*   **`VariableStorageComponent`**: Used to store and retrieve the `player_id` associated with the perk.