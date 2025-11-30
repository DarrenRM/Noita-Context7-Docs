---
title: Anti-Homing Component
category: entities
---

# Anti-Homing Component

This component is used to create entities that actively repel or negate homing projectiles.

## Key Attributes

*   **`homing_targeting_coeff`**: A negative coefficient that dictates the strength of the anti-homing effect. A larger negative value means a stronger repulsion.
*   **`homing_velocity_multiplier`**: A multiplier that affects the velocity of projectiles attempting to home in on this entity. A value less than 1 will slow them down, while a value greater than 1 would theoretically speed them up (though typically used for slowing).

## Example Usage

This component is typically attached to an entity that should act as a deterrent to homing projectiles. For instance, it could be applied to a specific type of enemy, a defensive structure, or even a special projectile that itself has anti-homing properties.

```xml
<Entity >
	<HomingComponent
		homing_targeting_coeff="-130.0"
		homing_velocity_multiplier="0.86"
	>
	</HomingComponent>
</Entity>
```