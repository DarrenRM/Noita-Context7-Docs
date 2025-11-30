---
title: Wand Charm Logic
category: scripts
---

# Wand Charm Logic

This script defines the behavior for the "Wand Charm" mechanic in Noita, which triggers when a player picks up certain items. It primarily handles the transformation of empty wands and the summoning of charmed entities.

## Core Functionality

The `material_area_checker_success` function is the main entry point for this script. It's called when an entity is picked up, and it determines the subsequent actions based on the type of entity and its properties.

### Key Actions:

1.  **Empty Wand Transformation:** If the picked-up entity is a wand and contains no spell cards, it is converted into a pile of golden nuggets. The number of nuggets is determined by the wand's level.
2.  **Charmed Entity Summoning:** If the picked-up entity is not an empty wand, the script attempts to summon a "wand ghost" entity.
    *   If the picked-up item is a "Sampo" (a special item), a `wand_ghost_with_sampo.xml` is summoned.
    *   Otherwise, a `wand_ghost_charmed.xml` is summoned.
3.  **Item Transfer and Validation:** The summoned ghost entity is configured to pick up the original item. The script then verifies that the ghost successfully acquired the item. If not, the ghost is destroyed to prevent potential issues.

## Helper Functions

### `wand_has_any_cards_in_it(wand_entity)`

This function checks if a given wand entity contains any spell cards.

*   **Input:** `wand_entity` (Entity ID of the wand)
*   **Output:** `true` if the wand has at least one card, `false` otherwise.
*   **Logic:** Iterates through all children of the wand entity and checks for the presence of an `ItemActionComponent`, which is associated with spell cards.

## Key Entities and Components Involved

*   **`ItemActionComponent`**: Indicates the presence of a spell card within a wand.
*   **`AbilityComponent`**: Used to retrieve the `gun_level` of a wand.
*   **`ItemPickUpperComponent`**: Allows an entity to pick up other entities. This is crucial for the charmed ghost to acquire the original item.
*   **`CameraBoundComponent`**: A component that might be removed from "Sampo" items.
*   **`EntityLoad()`**: Function to spawn new entities.
*   **`EntityKill()`**: Function to destroy entities.
*   **`EntityAddTag()`**: Function to add tags to entities.
*   **`EntityHasTag()`**: Function to check if an entity has a specific tag.
*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity that was just interacted with (picked up).
*   **`GamePickUpInventoryItem()`**: Simulates picking up an item.
*   **`GameGetAllInventoryItems()`**: Retrieves all items currently held by an entity.

## Configuration Parameters (Implicit)

While not explicitly listed as parameters, the script relies on the existence and properties of specific entity XML files:

*   `data/entities/particles/gold_pickup_large.xml`
*   `data/entities/items/pickup/goldnugget_200.xml`
*   `data/entities/animals/wand_ghost_with_sampo.xml`
*   `data/entities/animals/wand_ghost_charmed.xml`

The behavior is also influenced by tags like `"wand"` and `"this_is_sampo"`.