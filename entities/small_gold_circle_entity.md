---
title: Small Gold Circle Entity
category: entities
---

# Small Gold Circle Entity

This document describes the `empty_circle_small_gold.xml` entity, designed for AI-assisted modding of Noita.

## Entity Description

This entity represents a small, gold-colored circle that consumes nearby cells.

## Key Components and Attributes

### `CellEaterComponent`

This component defines the entity's ability to consume cells.

| Attribute        | Value   | Description                                                                 |
| :--------------- | :------ | :-------------------------------------------------------------------------- |
| `eat_probability`| `100`   | The probability (0-100) that the entity will eat a cell. 100 means it always eats. |
| `radius`         | `8`     | The radius around the entity within which it can eat cells.                 |
| `ignored_material`| `gold_box2d` | The material that this entity will ignore when eating cells.                |

### `LifetimeComponent`

This component controls how long the entity exists.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `10`  | The duration (in seconds) the entity will exist before despawning. |

## XML Structure

```xml
<Entity>
	<InheritTransformComponent>
    </InheritTransformComponent>
	
    <CellEaterComponent
		eat_probability="100"
        radius="8"
		ignored_material="gold_box2d"
		>
    </CellEaterComponent>
	
	<LifetimeComponent
		lifetime="10"
		>
	</LifetimeComponent>
  
</Entity>
```