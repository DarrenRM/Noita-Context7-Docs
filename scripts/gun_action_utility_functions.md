---
title: Gun Action Utility Functions
category: scripts/
---

# Gun Action Utility Functions

This document outlines utility functions for manipulating gun actions within Noita mods. These functions are primarily used to add, attach, and identify gun actions and wands.

## Core Functions

### `AddGunActionPermanent( entity_id, action_id )`

Attaches a specified gun action to an entity permanently. This function also increases the wand's deck capacity by one.

*   **`entity_id`**: The ID of the entity (typically a wand) to attach the action to.
*   **`action_id`**: The ID of the gun action entity to create and attach.

**Key Actions:**
1.  Creates a new item action entity based on `action_id`.
2.  Adds the created action as a child to the `entity_id`.
3.  Increases the `deck_capacity` of the `AbilityComponent` on the `entity_id` by 1.
4.  Sets the `permanently_attached` property of the action's `ItemComponent` to "1".
5.  Disables components tagged with "enabled\_in\_world" on the newly attached action.

### `AddGunAction( entity_id, action_id )`

Attaches a specified gun action to an entity. This is a non-permanent attachment.

*   **`entity_id`**: The ID of the entity (typically a wand) to attach the action to.
*   **`action_id`**: The ID of the gun action entity to create and attach.

**Key Actions:**
1.  Creates a new item action entity based on `action_id`.
2.  Adds the created action as a child to the `entity_id`.
3.  Disables components tagged with "enabled\_in\_world" on the newly attached action.

## Wand Identification Functions

### `find_the_wand_held( entity_id )`

Attempts to find the primary wand entity currently held by a given entity. It prioritizes the active item in `Inventory2Component` if it's a wand, otherwise it searches through children.

*   **`entity_id`**: The ID of the entity to search for a held wand (e.g., the player).
*   **Returns**: The entity ID of the found wand, or `0` if no wand is found.

**Search Logic:**
1.  Checks the `Inventory2Component` for an `mActiveItem` that has the "wand" tag.
2.  If not found, recursively searches through all children of the `entity_id` for entities with the "wand" tag.
3.  Prioritizes wands with an enabled `ItemComponent`.

### `find_all_wands_held( entity_id )`

Finds all wand entities that are children of a given entity.

*   **`entity_id`**: The ID of the entity to search for wands (e.g., the player).
*   **Returns**: A table containing the entity IDs of all found wands.

**Recursive Search:**
This function uses a helper function (`IMPL_find_all_wands_held`) to recursively traverse the entity's children and collect all entities tagged as "wand".