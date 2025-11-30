---
title: Moon Altar Initialization Script
category: scripts
---

# Moon Altar Initialization Script

This script handles the initialization logic for the Moon Altar, specifically checking for a persistent flag that alters its behavior.

## Core Functionality

The primary purpose of this script is to conditionally spawn a "newsun" entity if the `moon_is_sun` persistent flag is active.

### Key Elements

*   **`entity_id`**: Retrieves the unique identifier for the entity running this script.
*   **`x`, `y`**: Gets the current world coordinates of the entity.
*   **`HasFlagPersistent("moon_is_sun")`**: Checks if the persistent game flag named "moon_is_sun" is set. This flag likely indicates a special game state where the Moon Altar should behave differently.
*   **`EntityLoad("data/entities/items/pickup/sun/newsun.xml", x, y)`**: If the `moon_is_sun` flag is true, this function is called to load and spawn the `newsun.xml` entity at the Moon Altar's current position. This suggests that when this flag is active, the Moon Altar might transform into or spawn a sun-like entity.

## Usage Context

This script is intended to be attached to an entity representing the Moon Altar within the game's data files. Its execution is triggered during the game's entity initialization phase.