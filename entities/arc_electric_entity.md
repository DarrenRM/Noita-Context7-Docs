---
title: Arc Electric Entity
category: entities
---

# Arc Electric Entity

This document describes the `arc_electric.xml` entity, which represents an electrical arc effect in Noita.

## Entity Definition

The `arc_electric.xml` entity is a simple entity primarily defined by its `ArcComponent`.

```xml
<Entity >
	<LightningComponent>
	</LightningComponent>

	<ArcComponent
		type="LIGHTNING"
		lifetime="120" 
		material="" >
	</ArcComponent>
</Entity>
```

## Key Components and Attributes

### ArcComponent

This component defines the behavior and properties of the electrical arc.

*   **`type`**: Specifies the type of arc. In this case, it's set to `"LIGHTNING"`.
*   **`lifetime`**: The duration of the arc in frames. Here, it's set to `120` frames.
*   **`material`**: The material associated with the arc. This is left empty (`""`) in this specific configuration, implying it might inherit material properties or not have a distinct one for its visual representation.

### LightningComponent

This component is present but has no attributes defined. Its presence likely signifies that the entity is intended to interact with or generate lightning effects, even if the specific parameters are handled by the `ArcComponent`.