---
title: Furniture Dresser Prop
category: guides
---

<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<PhysicsImageShapeComponent 
			image_file="data/props_gfx/furniture_dresser.png"
			material="wood_prop"
			>
		</PhysicsImageShapeComponent>
	</Base>
</Entity>
```

---
title: Furniture Dresser Prop
category: entities
---

# Furniture Dresser Prop

This document describes the `furniture_dresser.xml` entity, which represents a dresser prop in Noita.

## Key Attributes

The dresser is a simple prop entity that inherits its physics behavior from `base_item_physics2.xml`.

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: This indicates that the dresser uses the standard physics properties for movable items in the game.

### Physics Image Shape Component

*   **`PhysicsImageShapeComponent`**: This component defines the visual representation and physical properties of the dresser.
    *   **`image_file="data/props_gfx/furniture_dresser.png"`**: Specifies the image file used for the dresser's sprite.
    *   **`material="wood_prop"`**: Assigns the "wood_prop" material to the dresser, which influences its interaction with physics and other game elements.