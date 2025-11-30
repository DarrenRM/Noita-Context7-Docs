---
title: Water Potion Item
category: entities
---

---

# Water Potion Item

This document describes the `potion_water.xml` entity, which represents a water potion pickup in Noita.

## Entity Definition

The `potion_water.xml` entity inherits its base properties from `data/entities/items/pickup/potion.xml`.

### Key Components

*   **Base File:** `data/entities/items/pickup/potion.xml`
    *   This indicates that the water potion shares fundamental characteristics with other potion items.
*   **Lua Component:**
    *   `script_source_file="data/scripts/items/potion_water.lua"`
        *   This component links the visual and physical representation of the potion to its specific behavior defined in the Lua script. This script will handle what happens when the potion is picked up or used.

## Lua Script (`data/scripts/items/potion_water.lua`)

While the XML defines the item's existence and its associated script, the actual functionality of the water potion is determined by its Lua script. This script would typically handle:

*   **Player Interaction:** What happens when the player touches or picks up the potion.
*   **Effect Application:** The specific effect the potion has (e.g., healing, status effect, or in this case, likely related to water properties).
*   **Consumption:** How the potion is consumed or its effect is triggered.

**Note:** The specific logic within `potion_water.lua` is not provided in the XML source, but it is the crucial element for understanding the potion's behavior.