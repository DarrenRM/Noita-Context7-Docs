---
title: Blood Money (10 HP) Item
category: entities
---

# Blood Money (10 HP) Item

This document describes the `bloodmoney_10.xml` entity, representing a pickup item in Noita that provides 10 HP.

## Entity Definition

The core of this item is defined by the `<Entity>` tag.

```xml
<Entity name="unknown" tags="item_physics,gold_nugget" >
    <!-- ... -->
</Entity>
```

*   **`name`**: "unknown" - This is a placeholder and not directly used for in-game identification.
*   **`tags`**: `item_physics`, `gold_nugget` - These tags categorize the item for game mechanics, indicating it has physical properties and is related to gold nuggets.

## Base Entity

The item inherits properties from a base entity.

```xml
<Base file="data/entities/items/pickup/goldnugget_10.xml" >
    <!-- ... -->
</Base>
```

This indicates that `bloodmoney_10.xml` is a variation of the `goldnugget_10.xml` item, likely sharing many fundamental characteristics.

### UI Information

This component defines how the item appears in the user interface.

```xml
<UIInfoComponent
    name="$item_bloodmoney" >
</UIInfoComponent>
```

*   **`name`**: `$item_bloodmoney` - This is a localization key that will be translated into the in-game display name for the item (e.g., "Blood Money").

### Physics and Shape

This component defines the physical properties and collision shape of the item.

```xml
<PhysicsImageShapeComponent
    material="bloodgold_box2d" >
</PhysicsImageShapeComponent>
```

*   **`material`**: `bloodgold_box2d` - Specifies the material used for physics interactions, likely influencing its weight and how it behaves when dropped or thrown.

### Item Component

This component marks the entity as an item that can be picked up.

```xml
<ItemComponent
    _tags="enabled_in_world"
    item_name="$item_bloodmoney_10"
    >
</ItemComponent>
```

*   **`_tags`**: `enabled_in_world` - Ensures the item is active and interactable when present in the game world.
*   **`item_name`**: `$item_bloodmoney_10` - Another localization key, likely for a more specific identifier or tooltip related to this particular variant.

## Variable Storage

This component stores custom variables for the entity.

```xml
<VariableStorageComponent
    _tags="enabled_in_world"
    name="hp_value"
    value_float="0.16" >
</VariableStorageComponent>
```

*   **`name`**: `hp_value` - This variable stores the health value this item provides.
*   **`value_float`**: `0.16` - Represents the amount of HP restored when this item is consumed. The comment indicates this value was adjusted to make 10 HP nuggets more impactful for healing.