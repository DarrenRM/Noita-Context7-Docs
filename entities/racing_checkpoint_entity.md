---
title: Racing Checkpoint Entity
category: entities
---

---

# Racing Checkpoint Entity

This document describes the `racing_checkpoint.xml` entity, which defines a checkpoint used in racing game modes within Noita.

## Key Components

### LightComponent
This component defines the visual appearance of the checkpoint.

*   **radius**: The radius of the light emitted by the checkpoint.
*   **r**: The red component of the light's color (0-255).
*   **g**: The green component of the light's color (0-255).
*   **b**: The blue component of the light's color (0-255).

```xml
<Entity tags="racing_checkpoint">
	<LightComponent 
		radius="100"
		r="255"
		g="80"
		b="80" >
	</LightComponent>
</Entity>
```

## Notes

*   Additional tags are applied to this entity via the `lavalake_racing.lua` script, which likely handles its functional behavior within a racing context.