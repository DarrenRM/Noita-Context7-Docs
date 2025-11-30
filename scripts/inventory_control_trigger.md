---
title: Inventory Control Trigger
category: scripts
---

---

# Inventory Control Trigger

This script defines a function `collision_trigger` that is intended to be used with entities that have the "controls_inventory" tag. When triggered, it iterates through all components of the closest entity with this tag and enables them.

## Key Functionality

### `collision_trigger()`

This function is the core of the script. It performs the following actions:

1.  **Finds Target Entity:** It searches for the closest entity that possesses the tag `"controls_inventory"`.
2.  **Retrieves Components:** It then retrieves all components associated with the found entity.
3.  **Enables Components:** If components are found, it iterates through each one and sets its enabled state to `true`.

## Usage Notes

*   This script is designed to be attached to an entity that acts as a trigger (e.g., a collision trigger).
*   The target entity must have the `"controls_inventory"` tag for this script to function correctly.
*   The primary purpose is to ensure that all components of an inventory-controlling entity are active when the trigger is activated.

## Example Scenario

Imagine an entity that manages a player's inventory. This `collision_trigger` function could be attached to a pressure plate. When the player steps on the pressure plate, the `collision_trigger` function is called, ensuring that all parts of the inventory management system are enabled and ready to function.