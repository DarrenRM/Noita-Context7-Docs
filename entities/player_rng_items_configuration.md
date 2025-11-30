---
title: Player RNG Items Configuration
category: entities
---

# Player RNG Items Configuration

This XML file defines the player entity and its initial inventory, specifically focusing on randomly generated items.

## Player Entity Definition

The main `<Entity>` tag defines the player character with several key tags:

*   **`name`**: `DEBUG_NAME:player` - Primarily for debugging purposes.
*   **`tags`**: A collection of tags that define the player's properties and interactions within the game. Key tags include:
    *   `mortal`: The player can die.
    *   `human`: Identifies the player as a human character.
    *   `hittable`: The player can be damaged.
    *   `player_unit`: Essential tag for identifying the player character.
    *   `teleportable`: The player can be teleported.

### Base Player Properties

*   **`<Base file="data/entities/player_base.xml" include_children="1" />`**: This element inherits all the fundamental properties and components of the player from `player_base.xml`, ensuring a consistent player foundation.

## Initial Inventory Setup

The player's starting inventory is configured within nested `<Entity>` tags.

### Quick Inventory (`inventory_quick`)

This section defines items that are immediately available to the player.

*   **`<Entity><Base file="data/entities/items/starting_wand_rng_daily.xml" /></Entity>`**: Grants the player a randomly generated wand for the current daily run.
*   **`<Entity><Base file="data/entities/items/starting_bomb_wand_rng_daily.xml" /></Entity>`**: Grants the player a randomly generated bomb wand for the current daily run.
*   **`<Entity><Base file="data/entities/items/pickup/potion.xml" /></Entity>`**: Includes a basic potion item in the quick inventory.

### Full Inventory (`inventory_full`)

*   **`<Entity name="inventory_full"/>`**: This tag likely represents the player's full inventory, which can be populated with items found during gameplay. The specific contents are not defined here but are managed by other game systems.