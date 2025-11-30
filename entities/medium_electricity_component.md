---
title: Medium Electricity Component
category: entities
---

# Medium Electricity Component

This entity defines a medium-strength electrical discharge.

## Entity Definition

The core of this entity is the `ElectricityComponent`.

### Key Attributes

*   **`energy`**: The amount of energy this electrical component carries.
    *   Value: `250`
*   **`probability_to_heat`**: The chance that this electrical discharge will cause heating.
    *   Value: `0.2` (20%)

```xml
<Entity>
	<ElectricityComponent
		energy="250"
		probability_to_heat="0.2" >
	</ElectricityComponent>
</Entity>
```