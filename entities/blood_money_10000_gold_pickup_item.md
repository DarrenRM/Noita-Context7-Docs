---
title: Blood Money (10000 Gold) Pickup Item
category: entities
---

# Blood Money (10000 Gold) Pickup Item

This document describes the `bloodmoney_10000.xml` entity, which represents a pickup item in Noita that grants a significant amount of gold.

## Key Attributes

This item inherits its base properties from `goldnugget_10000.xml` and modifies them to represent a large gold value.

### Entity Definition

```xml
<Entity name="unknown" tags="item_physics,gold_nugget" >
```

*   **`name`**: "unknown" - This is a placeholder and doesn't significantly impact functionality.
*   **`tags`**: `item_physics`, `gold_nugget` - These tags define its physical interaction and categorize it as a gold item.

### Base Entity

```xml
	<Base file="data/entities/items/pickup/goldnugget_10000.xml" >
```

*   This indicates that the item inherits most of its core properties from the `goldnugget_10000.xml` file.

### UI Information

```xml
		<UIInfoComponent
			name="$item_bloodmoney" >
		</UIInfoComponent>
```

*   **`name`**: `$item_bloodmoney` - This is a localization key that will be translated into the in-game display name for the item (e.g., "Blood Money").

### Physics Shape

```xml
		<PhysicsImageShapeComponent
			material="bloodgold_box2d" >
		</PhysicsImageShapeComponent>
```

*   **`material`**: `bloodgold_box2d` - This defines the physical material properties for collision and interaction within the game world.

### Item Component

```xml
		<ItemComponent
			_tags="enabled_in_world"
			item_name="$item_bloodmoney_10000"
			>
		</ItemComponent>
```

*   **`_tags`**: `enabled_in_world` - Ensures this item is active and interactable when placed in the game world.
*   **`item_name`**: `$item_bloodmoney_10000` - Another localization key, likely used for internal referencing or specific game logic related to this particular gold value.

### Variable Storage

```xml
	<VariableStorageComponent
		_tags="enabled_in_world"
		name="hp_value"
		value_float="0.6" >
	</VariableStorageComponent>
```

*   **`name`**: `hp_value` - This component stores a numerical value.
*   **`value_float`**: `0.6` - While named `hp_value`, in the context of gold pickups, this likely represents a multiplier or a base value that, when combined with other factors (like the base `goldnugget_10000.xml`), results in the 10000 gold value. The comment `<!-- 3*100 / 25 = 12.0 -->` suggests a calculation that might be related to how this `hp_value` contributes to the final gold amount, though the exact formula isn't directly in this XML.