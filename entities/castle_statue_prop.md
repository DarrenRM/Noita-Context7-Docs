---
title: Castle Statue Prop
category: entities
---

---

# Castle Statue Prop

This document describes the `furniture_castle_statue.xml` entity, which represents a decorative statue found in castle environments within Noita.

## Entity Definition

The core of this entity is defined by its `name` attribute and its inheritance from `base_item_physics2.xml`.

```xml
<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<!-- ... components ... -->
	</Base>
</Entity>
```

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the statue.

| Attribute     | Value                               | Description                                                                 |
|---------------|-------------------------------------|-----------------------------------------------------------------------------|
| `image_file`  | `data/props_gfx/furniture_castle_statue.png` | Specifies the image file used for the statue's sprite.                      |
| `material`    | `rock_box2d`                        | Defines the physical material properties, influencing its interaction with physics. |