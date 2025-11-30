---
title: Dark Moon Altar Initialization
category: scripts
---

---

# Dark Moon Altar Initialization

This script handles the initialization logic for the Dark Moon Altar, specifically its behavior when the "darkmoon_is_darksun" persistent flag is active.

## Core Functionality

The primary function of this script is to conditionally spawn a "newsun_dark" entity at the altar's location if a specific game state flag is set.

### Key Attributes

*   **`entity_id`**: The unique identifier for the entity running this script.
*   **`x`, `y`**: The world coordinates of the entity.
*   **`HasFlagPersistent("darkmoon_is_darksun")`**: A conditional check. If this persistent flag is true, the subsequent action is executed.
*   **`EntityLoad("data/entities/items/pickup/sun/newsun_dark.xml", x, y)`**: This function is called to load and place the `newsun_dark.xml` entity at the current `x`, `y` coordinates. This entity likely represents a dark sun pickup or a related visual/functional element.

## Dependencies

*   `dofile_once("data/scripts/lib/utilities.lua")`: Imports utility functions, though none are explicitly used in this minimal example.

## Usage Context

This script is intended to be attached to an entity that acts as the Dark Moon Altar. Its execution is tied to a specific game progression or state managed by the `darkmoon_is_darksun` flag.