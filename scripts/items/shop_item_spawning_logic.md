---
title: Shop Item Spawning Logic
category: scripts/items
---

# Shop Item Spawning Logic

This script dictates the random generation of items within Noita's shops. It determines the probability of spawning a standard shop item versus more specific types like potions or wands.

## Core Functionality

The script utilizes a pseudo-random number generator seeded by the entity's position to ensure consistent spawning for a given location.

### Item Generation Probabilities

The primary logic revolves around a series of random checks to decide which type of item to spawn:

*   **Standard Shop Item:** There is a 90% chance (`Random(1, 100) <= 90`) to spawn a general shop item by calling `generate_shop_item(x, y, false)`.
*   **Special Item Fallback:** If a standard shop item is *not* spawned (10% chance), the script proceeds to a secondary set of checks for rarer items.

### Special Item Spawning

Within the 10% fallback for special items:

*   **Potions:** There's a 25% chance (`Random(1, 100) <= 25`) to spawn a `shop_potion.xml`.
*   **Wands:** If a potion is not spawned (75% chance), a `shop_wand_level_01.xml` is spawned.

## Key Functions and Dependencies

*   `dofile_once("data/scripts/items/generate_shop_item.lua")`: This is the primary function for generating standard shop items.
*   `GetUpdatedEntityID()`: Retrieves the unique identifier for the current entity.
*   `EntityGetTransform(entity_id)`: Gets the position (x, y) of the entity.
*   `SetRandomSeed(x, y)`: Initializes the random number generator based on the entity's coordinates.
*   `Random(min, max)`: Generates a random integer within the specified range.
*   `EntityLoad(entity_xml_path, x, y)`: Loads a specific entity from its XML definition at the given coordinates.

## Example Entity Spawns

The script directly references the following entity XML files for spawning:

*   `data/entities/items/shop_card_creator.xml` (Commented out, likely an older or alternative spawn)
*   `data/entities/items/shop_potion.xml`
*   `data/entities/items/shop_cape.xml` (Commented out, likely an older or alternative spawn)
*   `data/entities/items/shop_wand_level_01.xml`