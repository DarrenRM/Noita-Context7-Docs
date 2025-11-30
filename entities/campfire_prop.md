---
title: Campfire Prop
category: entities
---

# Campfire Prop

This document describes the `physics_campfire.xml` entity, which represents a campfire prop in Noita.

## Entity Definition

The core entity definition for the campfire.

```xml
<Entity name="unknown" >
  <!-- ... components ... -->
</Entity>
```

## Key Components

### PhysicsBodyComponent

This component defines the physical properties of the campfire.

| Attribute        | Description                                                                 |
| ------------------ | --------------------------------------------------------------------------- |
| `allow_sleep`      | `1` - Allows the physics body to go to sleep when not in use, optimizing performance. |
| `fixed_rotation`   | `0` - Allows the campfire to rotate.                                        |
| `is_bullet`        | `0` - Indicates this is not a projectile.                                   |
| `auto_clean`       | `0` - The entity will not be automatically removed after a certain time.    |
| `on_death_leave_physics_body` | `1` - Leaves a physics body behind when destroyed.                      |

### PhysicsImageShapeComponent

This component defines the visual shape and material of the campfire.

| Attribute    | Description                                     |
| -------------- | ----------------------------------------------- |
| `image_file` | `data/props_gfx/campfire.png` - The sprite for the campfire. |
| `material`   | `wood_prop_durable` - The physical material properties. |

### CameraBoundComponent

This component controls how the campfire interacts with the camera's view.

| Attribute   | Description                                                              |
| ----------- | ------------------------------------------------------------------------ |
| `max_count` | `50` - The maximum number of these entities that can be active within the camera's view. |
| `distance`  | `500` - The maximum distance from the camera at which this entity will be rendered. |