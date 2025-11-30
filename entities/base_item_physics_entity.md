---
title: Base Item Physics Entity
category: entities
---

---

# Base Item Physics Entity

This document describes the base entity for physics-based items in Noita, often used for props and objects that interact with the game's physics engine.

## Key Components and Attributes

### PhysicsBodyComponent

This component governs the physical properties of the entity.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `allow_sleep`       | If `1`, the body can enter a sleep state when not in motion to save performance. |
| `angular_damping`   | Resistance to rotational motion. `0` means no resistance.                |
| `fixed_rotation`    | If `1`, the entity's rotation is locked.                                 |
| `is_bullet`         | If `1`, the body is treated as a bullet (e.g., for collision detection). |
| `linear_damping`    | Resistance to linear motion. `0` means no resistance.                  |
| `on_death_really_leave_body` | If `1`, the body is completely removed upon death.                   |

### PhysicsImageShapeComponent

This component defines the visual shape and physical material of the entity based on an image.

| Attribute    | Description                                                              |
| :----------- | :----------------------------------------------------------------------- |
| `centered`   | If `1`, the image is centered on the entity's origin.                    |
| `image_file` | Path to the image file used for the entity's shape and appearance.       |
| `material`   | The physical material of the entity, affecting its interaction with other physics objects (e.g., "steel", "wood"). |

## Example Usage

```xml
<Entity tags="hittable,teleportable_NOT,prop,prop_physics">
  <PhysicsBodyComponent 
	allow_sleep="1"
	angular_damping="0"
	fixed_rotation="0"
	is_bullet="0"
	linear_damping="0" 
	on_death_really_leave_body="0"
	>
  </PhysicsBodyComponent>

  <PhysicsImageShapeComponent 
    centered="1" 
    image_file="data/temp/landmine.png"
    material="steel" >
  </PhysicsImageShapeComponent>

</Entity>
```