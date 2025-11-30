---
title: Beer Potion Pickup
category: entities
---

# Beer Potion Pickup

This document describes the `potion_beer.xml` entity, which represents a beer potion pickup in Noita.

## Entity Definition

The `potion_beer.xml` entity inherits its base properties from `data/entities/items/pickup/potion.xml`.

### Key Components

*   **`Base`**: Inherits core functionality from `data/entities/items/pickup/potion.xml`.
*   **`VariableStorageComponent`**:
    *   `name`: `potion_material`
    *   `value_string`: `beer`
        *   This attribute is crucial as it defines the specific type of potion. In this case, it designates the potion as "beer."

This setup allows for a modular approach to potion creation, where different potion types can be defined by simply changing the `value_string` in the `VariableStorageComponent` while reusing the base potion logic.