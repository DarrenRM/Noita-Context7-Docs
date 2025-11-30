---
title: Magic Convert Material Component
category: entities
---

# Magic Convert Material Component

This component allows a magical entity to convert one material into another.

## Key Attributes

*   **`from_material`**: The material that will be converted.
*   **`to_material`**: The material that the `from_material` will be converted into.

## Usage Example

This example demonstrates a magical entity that converts water into blood.

```xml
<Entity >
	<MagicConvertMaterialComponent
		from_material="water"
		to_material="blood" >
	</MagicConvertMaterialComponent>
</Entity>
```