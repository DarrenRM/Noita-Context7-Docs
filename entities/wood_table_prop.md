---
title: Wood Table Prop
category: entities
---

---

# Wood Table Prop

This document describes the `furniture_wood_table.xml` entity, a basic wooden table prop for Noita.

## Entity Definition

The core of this entity is defined by its `name` and its `Base` file, which inherits physics and rendering properties.

```xml
<Entity name="unknown" >
	<Base file="data/entities/base_item_physics2.xml" >
		<!-- ... -->
	</Base>
</Entity>
```

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the table.

| Attribute     | Value                               | Description                                                                 |
|---------------|-------------------------------------|-----------------------------------------------------------------------------|
| `image_file`  | `data/props_gfx/furniture_wood_table.png` | Specifies the image file used for the table's sprite.                     |
| `material`    | `wood_prop`                         | Defines the material type, influencing its physical interactions (e.g., damage). |