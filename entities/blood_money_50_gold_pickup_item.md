---
title: Blood Money (50 Gold) Pickup Item
category: entities
---

# Blood Money (50 Gold) Pickup Item

This document describes the `bloodmoney_50.xml` entity, which represents a pickup item in Noita that grants 50 gold.

## Entity Definition

The entity is named "unknown" and has the tags `item_physics` and `gold_nugget`.

```xml
<Entity name="unknown" tags="item_physics,gold_nugget" >
```

## Base Entity

This item inherits its base properties from `data/entities/items/pickup/goldnugget_50.xml`.

```xml
	<Base file="data/entities/items/pickup/goldnugget_50.xml" >
```

### UI Information

Defines the in-game name for the item.

```xml
		<UIInfoComponent
			name="$item_bloodmoney" >
		</UIInfoComponent>
```

### Physics Shape

Specifies the physical properties of the item's collision shape.

```xml
		<PhysicsImageShapeComponent
			material="bloodgold_box2d" >
		</PhysicsImageShapeComponent>
```

### Item Component

Marks the item as enabled in the game world.

```xml
		<ItemComponent
			_tags="enabled_in_world"
			item_name="$item_bloodmoney_50"
			>
		</ItemComponent>
```

## Variable Storage

This component stores a specific variable related to the item's functionality.

### HP Value

Stores a float value representing the "hp_value". The comment suggests a calculation related to gold conversion (3*5 / 25 = 0.6), implying this might be a multiplier or a base value for gold generation or consumption in certain contexts.

```xml
	<VariableStorageComponent
		_tags="enabled_in_world"
		name="hp_value"
		value_float="0.4" >
	</VariableStorageComponent>
```