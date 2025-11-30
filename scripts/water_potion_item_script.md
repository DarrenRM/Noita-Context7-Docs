---
title: Water Potion Item Script
category: scripts
---

---

# Water Potion Item Script

This script defines the behavior for a water potion item in Noita.

## Core Functionality

The primary function of this script is to equip the player with a potion that contains a significant amount of "water" material.

### `init( entity_id )`

This function is called when the potion item is initialized in the game world.

*   **`entity_id`**: The unique identifier for the potion entity.
*   **Material Assignment**: It sets the potion's internal material to `"water"`.
*   **Material Quantity**: It adds `1000` units of the `"water"` material to the potion's inventory.

## Associated Data

### `materials_standard`

This table defines standard material properties, though it's not directly used by the `init` function for the water potion itself. It serves as a reference for material costs.

| Material | Cost |
| :------- | :--- |
| water    | 200  |