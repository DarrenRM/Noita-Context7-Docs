---
title: Statue Hand 2 Building Entity
category: entities
---

# Statue Hand 2 Building Entity

This document describes the `statue_hand_2.xml` entity, representing a specific type of statue hand building in Noita.

## Entity Definition

The core of this entity is its inheritance from `statue_hand_1.xml`, indicating it shares many fundamental properties with other statue hand entities.

```xml
<Entity tags="statue_hand_2,statue_hand">
	<Base file="data/entities/buildings/statue_hand_1.xml" >
		<PhysicsImageShapeComponent 
			image_file="data/buildings_gfx/statue_hand_2.png"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```

## Key Components and Attributes

### Base Entity

*   **`file`**: `data/entities/buildings/statue_hand_1.xml`
    *   This attribute signifies that `statue_hand_2` inherits its base properties and components from `statue_hand_1`. This is a common pattern for variations of existing entities.

### PhysicsImageShapeComponent

*   **`image_file`**: `data/buildings_gfx/statue_hand_2.png`
    *   Specifies the graphical asset used for this building's visual representation. This is the primary differentiator for the visual appearance of `statue_hand_2` compared to other statue hands.

### Tags

*   **`statue_hand_2`**: A unique tag for this specific entity.
*   **`statue_hand`**: A general tag shared with other statue hand entities, allowing for broader targeting in game logic or modding.

## Summary

The `statue_hand_2.xml` entity is a simple variation of the `statue_hand_1` building. Its primary distinction lies in its unique graphical asset (`statue_hand_2.png`), while inheriting most of its functional behavior from its base entity. This makes it straightforward to modify or extend for AI-assisted modding by focusing on the `PhysicsImageShapeComponent` for visual changes or by leveraging the inherited components from `statue_hand_1.xml`.