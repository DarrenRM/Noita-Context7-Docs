---
title: Homing Component - Short Range
category: entities
---

# Homing Component - Short Range

This entity defines a short-range homing behavior for projectiles or entities.

## Key Attributes

The `HomingComponent` controls how an entity targets and moves towards a specific point.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `homing_targeting_coeff`   | The strength of the homing force. Higher values mean faster targeting.      |
| `homing_velocity_multiplier` | Multiplies the entity's base velocity when homing.                          |
| `detect_distance`          | The maximum distance at which the entity can detect its target.             |

## XML Structure

```xml
<Entity>
	<HomingComponent
		homing_targeting_coeff="480.0"
		homing_velocity_multiplier="0.83"
		detect_distance="60"
	>
	</HomingComponent>
</Entity>
```