---
title: Blood Money Pickup Item
category: entities
---

# Blood Money Pickup Item

This document describes the `bloodmoney_200000.xml` entity, which represents a pickup item in Noita. It's a variation of the gold nugget, specifically designed to grant a significant amount of gold upon pickup.

## Key Components and Attributes

### Entity Definition

*   **`name`**: `unknown` (This is a placeholder and might be overridden by the base file or other components).
*   **`tags`**: `item_physics`, `gold_nugget` (Indicates it's a physics-based item and a type of gold nugget).

### Base Entity

*   **`file`**: `data/entities/items/pickup/goldnugget_200000.xml` (Inherits properties from a base gold nugget item).

### UI Information

*   **`UIInfoComponent`**:
    *   **`name`**: `$item_bloodmoney` (Defines the in-game name displayed for this item).

### Physics and Appearance

*   **`PhysicsImageShapeComponent`**:
    *   **`material`**: `bloodgold_box2d` (Specifies the physics material, likely influencing its interaction with the game world).

### Item Properties

*   **`ItemComponent`**:
    *   **`_tags`**: `enabled_in_world` (Ensures the item is active and interactable when in the game world).
    *   **`item_name`**: `$item_bloodmoney_200000` (A specific identifier for this blood money variant).

### Variable Storage

*   **`VariableStorageComponent`**:
    *   **`_tags`**: `enabled_in_world`
    *   **`name`**: `hp_value` (This component stores a numerical value associated with the item).
    *   **`value_float`**: `1.6` (This likely represents the gold value granted by the item. The comment `<!-- 3*100 / 25 = 12.0 -->` suggests a calculation that might have been intended for a different value or is a remnant, as `1.6` is the actual stored value).

---
```xml
<Entity name="unknown" tags="item_physics,gold_nugget" >

	<Base file="data/entities/items/pickup/goldnugget_200000.xml" >

		<!-- physical presence -->
		<UIInfoComponent
			name="$item_bloodmoney" >
		</UIInfoComponent>

		<PhysicsImageShapeComponent 
			material="bloodgold_box2d" >
		</PhysicsImageShapeComponent>

		<ItemComponent
			_tags="enabled_in_world"
			item_name="$item_bloodmoney_200000"
			>
		</ItemComponent>
	</Base>

	<!-- 3*100 / 25 = 12.0 -->
	<VariableStorageComponent
		_tags="enabled_in_world"
		name="hp_value"
		value_float="1.6" >
	</VariableStorageComponent>

	<!-- item -->


</Entity>
```