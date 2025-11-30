---
title: Homing Component
category: entities
---

# Homing Component

This component grants entities a homing behavior, causing them to pursue a target.

## Key Attributes

*   `homing_targeting_coeff`: Controls how strongly the entity attempts to target its destination. Higher values mean more aggressive pursuit.
*   `homing_velocity_multiplier`: Adjusts the entity's speed when actively homing. A value of 1.0 means it moves at its normal speed, while values less than 1.0 will slow it down.

## Usage

The `HomingComponent` is typically added to projectiles or enemies that need to track and follow a specific target.

```xml
<Entity >
	<HomingComponent
		homing_targeting_coeff="130.0"
		homing_velocity_multiplier="0.86"
	>
	</HomingComponent>
</Entity>
```