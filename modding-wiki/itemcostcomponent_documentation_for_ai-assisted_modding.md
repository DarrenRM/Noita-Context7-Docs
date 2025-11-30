---
title: ItemCostComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:ItemCostComponent
category: modding-wiki
---

# ItemCostComponent Documentation

This document details the `ItemCostComponent` in Noita, a crucial component for defining the cost of items within the game. Understanding and modifying this component is essential for creating balanced and engaging item economies in your mods. It covers how item costs are determined and how you can influence them through modding.

## Overview of ItemCostComponent

The `ItemCostComponent` is responsible for determining the price of an item in Noita. This price is primarily influenced by the item's base cost and any modifiers that can increase or decrease it. Modding this component allows you to adjust the economic balance of your game, making certain items rarer or more accessible.

## Component Properties

The `ItemCostComponent` has several properties that influence an item's cost. These are typically defined within the item's XML definition.

### `base_cost`

This is the fundamental cost of the item. It's a numerical value that serves as the starting point for all other cost calculations.

### `modifier_tags`

This is a list of tags that can modify the item's cost. Each tag can be associated with a specific cost multiplier or additive value, allowing for dynamic cost adjustments based on game state or item properties.

**Example:**

```xml
<ItemCostComponent
    base_cost="100"
    modifier_tags="tag_rare, tag_cursed"
/>
```

In this example, an item with a `base_cost` of 100 would have its cost further modified by the presence of `tag_rare` and `tag_cursed`. The exact effect of these tags would be defined elsewhere in the game's configuration or through other components.

## Modifying Item Costs

Modifying item costs can be achieved by directly altering the `base_cost` or by introducing new `modifier_tags` and their associated effects.

### Adjusting `base_cost`

The simplest way to change an item's cost is to directly edit its `base_cost` in its XML definition.

**Example:**

To make a potion cost less, you could change its `base_cost` from 50 to 25:

```xml
<Item name="Healing Potion">
    <ItemCostComponent
        base_cost="25"
    />
    <!-- Other components -->
</Item>
```

### Implementing Cost Modifiers

More complex cost adjustments can be achieved by leveraging `modifier_tags`. This requires understanding how these tags are interpreted by the game. Often, other components or game systems will read these tags and apply their effects.

**Example:**

Let's say you want to create a "cursed" version of an item that is cheaper. You could add a `tag_cursed` to its `modifier_tags` and then define the effect of `tag_cursed` elsewhere.

```xml
<Item name="Cursed Amulet">
    <ItemCostComponent
        base_cost="200"
        modifier_tags="tag_cursed"
    />
    <!-- Other components -->
</Item>
```

You would then need to ensure that the game's logic for `tag_cursed` reduces the item's cost. This might involve a separate component or a script that checks for this tag.

## Further Resources

For a deeper understanding of how components interact and how to implement custom logic, refer to the following:

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Component System Overview](https://noita.wiki.gg/wiki/Modding:_Components)