---
title: Darkness Chest
category: biome
---

---

# Darkness Chest

This documentation describes the `chest_darkness.lua` script, which defines the behavior of a special "Darkness Chest" entity in Noita. This chest has unique interactions when opened or picked up.

## Key Functions

### `on_open(entity_item)`

This function is called when the chest is opened.

*   **Spawns Particle Effect:** Loads `data/entities/particles/image_emitters/chest_effect.xml` at the chest's location.
*   **Creates Item Action:** Spawns a `TOUCH_GRASS` item action entity.
*   **Sets Persistent Flag:** Adds a persistent flag `card_unlocked_touch_grass`.

### `item_pickup(entity_item, entity_who_picked, name)`

This function is triggered when the chest is picked up by a player.

*   **Prints Message:** Displays an important game message: "$log\_chest".
*   **Calls `on_open`:** Executes the `on_open` function to trigger its effects.
*   **Kills Entity:** Removes the chest entity from the game.

### `physics_body_modified(is_destroyed)`

This function is called when the chest's physics body is modified (e.g., destroyed).

*   **Gets Updated Entity:** Retrieves the ID of the modified entity.
*   **Calls `on_open`:** Executes the `on_open` function.
*   **Disables Item Component:** Finds the `ItemComponent` and disables it.
*   **Kills Entity:** Removes the chest entity from the game.

## Summary

The Darkness Chest is designed to provide a specific gameplay event upon interaction. When opened or picked up, it triggers a visual effect, grants a special item action, and sets a persistent flag. The `physics_body_modified` function ensures that even if the chest is destroyed physically, its associated `on_open` logic is still executed before it's removed.