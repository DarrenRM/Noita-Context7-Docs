---
title: Milk Potion Pickup
category: entities
---

# Milk Potion Pickup

This document describes the `potion_milk.xml` entity, which represents a milk potion pickup in Noita.

## Entity Definition

The `potion_milk.xml` entity inherits its base functionality from `data/entities/items/pickup/potion.xml`.

### Key Components

*   **`Base`**: Inherits from `data/entities/items/pickup/potion.xml`, providing the fundamental properties of a potion pickup.
*   **`VariableStorageComponent`**:
    *   `name`: `potion_material`
    *   `value_string`: `milk`
        *   This component is crucial for identifying the specific type of potion. In this case, it designates the potion as "milk".

## Purpose

This entity defines an item that players can pick up in the game world. When collected, it will likely restore health or provide some other beneficial effect associated with milk. The `VariableStorageComponent` ensures that the game correctly identifies this pickup as a milk potion.