---
title: Player Entity Configuration
category: entities
---

# Player Entity Configuration

This document outlines the key configurations for the player entity in Noita, primarily focusing on its base properties and initial inventory setup.

## Core Entity Properties

The player entity is defined by its `name` and a set of `tags` that determine its behavior and interactions within the game world.

*   **`name`**: `DEBUG_NAME:player` - A descriptive name for internal use.
*   **`tags`**:
    *   `mortal`: Indicates the player can die.
    *   `human`: Identifies the player as a human-like entity.
    *   `hittable`: Allows the player to be targeted and damaged.
    *   `peasant`: A classification tag.
    *   `prey`: Suggests the player can be hunted by certain entities.
    *   `player_unit`: A primary tag identifying this as the player character.
    *   `teleportable`: Allows the player to be teleported.

## Base Entity Inclusion

The player entity inherits its fundamental properties and behaviors from a base configuration file.

*   **`<Base file="data/entities/player_base.xml" include_children="1" />`**: This directive includes all elements and attributes from `player_base.xml`, ensuring the player has all its core functionalities.

## Initial Inventory Setup

The player starts with a predefined set of items in their inventory.

*   **`<Entity name="inventory_quick">`**: This section defines the items available in the player's quick inventory slots.
    *   **`<Entity><Base file="data/entities/items/starting_wand_rng.xml" /></Entity>`**: The player begins with a randomly generated starting wand.
    *   **`<Entity><Base file="data/entities/items/starting_bomb_wand_rng.xml" /></Entity>`**: The player also starts with a randomly generated bomb wand.
    *   **`<Entity><Base file="data/entities/items/pickup/potion_starting.xml" /></Entity>`**: A starting potion is included.

*   **`<Entity name="inventory_full"/>`**: This element likely represents the full inventory capacity or a placeholder for additional inventory management logic.