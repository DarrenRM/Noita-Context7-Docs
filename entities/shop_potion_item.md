---
title: Shop Potion Item
category: entities
---

---

# Shop Potion Item

This document describes the `shop_potion.xml` entity, which defines a potion item available for purchase in the game's shops.

## Key Components

### Base Entity

*   **`data/entities/items/pickup/potion.xml`**: Inherits core properties and behaviors of a standard potion pickup.
*   **`data/entities/base_shop_item.xml`**: Inherits properties specific to items sold in shops.

### Item Cost Component

*   **`ItemCostComponent`**:
    *   **`cost`**: `150` - This attribute defines the price of the potion in the shop.

## Summary

The `shop_potion.xml` entity is a straightforward implementation that leverages existing base entity files to create a purchasable potion. Its primary defining characteristic is its cost, set to 150.