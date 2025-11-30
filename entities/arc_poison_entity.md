---
title: Arc Poison Entity
category: entities
---

# Arc Poison Entity

This document describes the `arc_poison.xml` entity, which represents a source of poison damage in Noita.

## Entity Definition

The `arc_poison.xml` file defines a simple entity with a single key component: `ArcComponent`.

```xml
<Entity>
	<ArcComponent
		lifetime="120" 
		material="poison" >
	</ArcComponent>
</Entity>
```

## Key Components and Attributes

### ArcComponent

This component dictates the behavior and properties of the arc poison.

*   **`lifetime`**: (float) The duration in seconds for which the poison effect will persist. In this case, it's set to `120` seconds.
*   **`material`**: (string) Specifies the material associated with this arc. This is crucial for determining the damage type and any associated effects. Here, it's set to `"poison"`.

## AI Modding Considerations

When modding AI entities that interact with or create poison effects, understanding the `ArcComponent` and its `material` attribute is essential.

*   **Damage Application**: The `"poison"` material likely signifies that entities or projectiles with this component will apply poison damage over time to anything they hit.
*   **Duration Control**: The `lifetime` attribute can be adjusted to control how long the poison effect lasts.
*   **Customization**: Modders could potentially create new poison materials with different damage values or effects by defining them elsewhere and referencing them here.