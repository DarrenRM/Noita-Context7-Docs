---
title: Blood Money (1000 Gold) Pickup Item
category: entities
---

# Blood Money (1000 Gold) Pickup Item

This document describes the `bloodmoney_1000.xml` entity, which represents a pickup item in Noita that grants 1000 gold.

## Entity Definition

The core of this item is defined by the `<Entity>` tag.

```xml
<Entity name="unknown" tags="item_physics,gold_nugget" >
    <!-- ... -->
</Entity>
```

*   **`name`**: "unknown" - This is a placeholder and doesn't significantly impact gameplay for this item.
*   **`tags`**: `item_physics`, `gold_nugget` - These tags are crucial for defining its behavior as a physical item that can be picked up and is recognized as a gold nugget.

## Base Item Inheritance

This item inherits properties from `goldnugget_1000.xml`, indicating it shares fundamental characteristics with other gold nuggets.

```xml
<Base file="data/entities/items/pickup/goldnugget_1000.xml" >
    <!-- ... -->
</Base>
```

## UI Information

This component defines how the item appears in the game's user interface.

```xml
<UIInfoComponent
    name="$item_bloodmoney" >
</UIInfoComponent>
```

*   **`name`**: `$item_bloodmoney` - This is a localization key that will be translated into the in-game name for the item (e.g., "Blood Money").

## Physics and Visuals

This component defines the physical shape and material of the item.

```xml
<PhysicsImageShapeComponent
    material="bloodgold_box2d" >
</PhysicsImageShapeComponent>
```

*   **`material`**: `bloodgold_box2d` - This specifies the material properties for physics interactions and potentially its visual appearance.

## Item Component

This component marks the entity as an item that can be interacted with and picked up.

```xml
<ItemComponent
    _tags="enabled_in_world"
    item_name="$item_bloodmoney_1000" >
</ItemComponent>
```

*   **`_tags`**: `enabled_in_world` - Ensures the item is active and present when the game world is loaded.
*   **`item_name`**: `$item_bloodmoney_1000` - Another localization key, likely for a more specific identifier or tooltip related to this particular gold amount.

## Variable Storage

This component stores a specific numerical value associated with the item.

```xml
<VariableStorageComponent
    _tags="enabled_in_world"
    name="hp_value"
    value_float="0.6" >
</VariableStorageComponent>
```

*   **`name`**: `hp_value` - While named `hp_value`, in the context of gold pickups, this likely represents the gold value or a multiplier related to it.
*   **`value_float`**: `0.6` - This float value is a key attribute. Given the item's name and the comment `<!-- 3*100 / 25 = 12.0 -->` (which seems to be a calculation for a different item or a misunderstanding), this `0.6` likely contributes to the total gold value. For a 1000 gold item, this might be a base value that is then scaled or directly represents a portion of the total. Further context from `goldnugget_1000.xml` would clarify its exact role in determining the 1000 gold.