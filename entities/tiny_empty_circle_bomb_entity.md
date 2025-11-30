---
title: Tiny Empty Circle Bomb Entity
category: entities
---

# Tiny Empty Circle Bomb Entity

This document describes the `empty_circle_tiny_bomb.xml` entity, designed for AI-assisted modding of Noita. This entity represents a small, ephemeral bomb that consumes cells.

## Key Components and Attributes

This entity primarily utilizes the following components:

### `CellEaterComponent`

This component defines the entity's ability to consume nearby cells.

*   **`eat_probability`**: `100` - The probability that this entity will eat a cell. A value of 100 means it will always attempt to eat.
*   **`radius`**: `8` - The radius around the entity within which it will attempt to eat cells.
*   **`ignored_material`**: `"fuse"` - Materials that this entity will not consume.

### `LifetimeComponent`

This component dictates how long the entity will exist before being destroyed.

*   **`lifetime`**: `10` - The duration in seconds for which the entity will remain active.

## XML Structure

```xml
<Entity>
	<InheritTransformComponent>
    </InheritTransformComponent>
	
    <CellEaterComponent
		eat_probability="100"
        radius="8"
		ignored_material="fuse"
		>
    </CellEaterComponent>
	
	<LifetimeComponent
		lifetime="10"
		>
	</LifetimeComponent>
  
</Entity>
```