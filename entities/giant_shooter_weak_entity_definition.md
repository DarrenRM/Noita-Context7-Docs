---
title: Giant Shooter (Weak) Entity Definition
category: entities
---

# Giant Shooter (Weak) Entity Definition

This document details the configuration for the "Giant Shooter (Weak)" entity in Noita, primarily focusing on its visual and combat attributes.

## Core Entity Configuration

The `GiantShooter_weak` entity inherits its base functionality from the standard `giantshooter.xml` file, with specific modifications to its health and visual representation.

```xml
<Entity name="$animal_giantshooter_weak">
  
	<Base file="data/entities/animals/giantshooter.xml" >
		<!-- ... other inherited components ... -->
	</Base>
	
	<!-- ... specific components for this variant ... -->

</Entity>
```

## Key Components and Attributes

### DamageModelComponent

This component defines the combat-related properties of the entity.

| Attribute           | Value      | Description                                                                 |
| :------------------ | :--------- | :-------------------------------------------------------------------------- |
| `ragdoll_filenames_file` | `data/ragdolls/giantshooter_weak/filenames.txt` | Specifies the files used for the entity's ragdoll physics upon death. |
| `hp`                | `2.0`      | The hit points of the weak variant of the Giant Shooter.                    |

### SpriteComponent

This component dictates the visual appearance of the entity.

| Attribute    | Value                             | Description                                                              |
| :----------- | :-------------------------------- | :----------------------------------------------------------------------- |
| `image_file` | `data/enemies_gfx/giantshooter_weak.xml` | Points to the XML file defining the sprite animations and frames. |

## Attached Entities (Tentacles)

The weak variant of the Giant Shooter also features several attached "slime tentacle" entities, contributing to its visual complexity and potentially its attack patterns. These are defined using `<Entity>` tags with `<Base>` components inheriting from specific tentacle prefabs.

### Tentacle Attachments

| Tentacle Prefab                                     | Position (x, y) | Description