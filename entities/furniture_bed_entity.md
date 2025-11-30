---
title: Furniture Bed Entity
category: entities
---

---

# Furniture Bed Entity

This document describes the `furniture_bed.xml` entity, which represents a bed prop in Noita.

## Entity Definition

The core of the entity is defined by the `<Entity>` tag.

```xml
<Entity name="unknown">
    <!-- ... -->
</Entity>
```

## Base Entity

This bed inherits properties from a base physics entity.

```xml
<Base file="data/entities/base_item_physics2.xml">
    <!-- ... -->
</Base>
```

## Physics and Graphics

The `PhysicsImageShapeComponent` defines the visual representation and physical properties of the bed.

### PhysicsImageShapeComponent

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `image_file` | Path to the sprite used for the bed.            |
| `material`  | The material type, affecting physics interactions. |

```xml
<PhysicsImageShapeComponent
    image_file="data/props_gfx/furniture_bed.png"
    material="wood_prop">
</PhysicsImageShapeComponent>
```