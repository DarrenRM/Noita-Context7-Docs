---
title: Statue Hand 3 Entity
category: entities
---

# Statue Hand 3 Entity

This document describes the `statue_hand_3.xml` entity, which represents a specific type of statue hand building in Noita. It inherits its base properties from `statue_hand_1.xml` and defines its visual representation.

## Key Attributes

*   **`tags`**: `statue_hand_3`, `statue_hand` - These tags categorize the entity and allow for specific interactions or targeting.

## Inheritance

*   **`Base`**: The entity inherits its fundamental properties and behaviors from `data/entities/buildings/statue_hand_1.xml`. This implies that `statue_hand_3` shares many characteristics with `statue_hand_1` unless explicitly overridden.

## Visual Component

*   **`PhysicsImageShapeComponent`**: This component defines the visual appearance of the statue hand.
    *   **`image_file`**: `data/buildings_gfx/statue_hand_1.png` - Specifies the image asset used for rendering the statue. Notably, it reuses the image from `statue_hand_1`, suggesting a visual similarity or a placeholder.

```xml
<Entity tags="statue_hand_3,statue_hand">
	<Base file="data/entities/buildings/statue_hand_1.xml" >
		<PhysicsImageShapeComponent 
			image_file="data/buildings_gfx/statue_hand_1.png"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```