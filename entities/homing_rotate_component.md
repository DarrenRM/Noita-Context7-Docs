---
title: Homing Rotate Component
category: entities
---

# Homing Rotate Component

This component enables an entity to rotate towards a target.

## Key Attributes

*   `just_rotate_towards_target`: A boolean value. When set to `1` (true), the entity will only rotate towards the target without moving.
*   `max_turn_rate`: A float value that defines the maximum speed at which the entity can turn. A higher value means faster rotation.

## Usage Example

```xml
<Entity >
	<HomingComponent
		just_rotate_towards_target="1"
		max_turn_rate="0.2"
	>
	</HomingComponent>
</Entity>
```