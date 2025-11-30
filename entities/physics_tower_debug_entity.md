---
title: Physics Tower Debug Entity
category: entities
---

# Physics Tower Debug Entity

This entity defines a debug structure composed of multiple physics-enabled planks connected by weld joints. It's primarily used for testing and visualizing physics interactions within the game engine.

## Key Components

### PhysicsBody2Component

This component defines the overall physical properties of the entity.

| Attribute              | Description                                                              |
| :--------------------- | :----------------------------------------------------------------------- |
| `allow_sleep`          | Whether the body can enter a sleep state to save performance.            |
| `angular_damping`      | Resistance to rotational motion.                                         |
| `linear_damping`       | Resistance to linear motion.                                             |
| `kill_entity_after_initialized` | If true, the entity is destroyed immediately after its physics are set up. |
| `init_offset_x`        | Initial offset on the X-axis when the entity is spawned.                 |
| `init_offset_y`        | Initial offset on the Y-axis when the entity is spawned.                 |

### PhysicsImageShapeComponent

These components define the visual and physical shape of individual planks. Each component represents a single plank.

| Attribute    | Description                                                              |
| :----------- | :----------------------------------------------------------------------- |
| `body_id`    | Unique identifier for the physics body this shape is attached to.        |
| `offset_x`   | Offset of the shape from the entity's origin on the X-axis.              |
| `offset_y`   | Offset of the shape from the entity's origin on the Y-axis.              |
| `image_file` | Path to the image file used for the visual representation of the plank.  |
| `material`   | The material type, affecting its physical properties (e.g., `wood_prop`). |

**Summary of `PhysicsImageShapeComponent` instances:**
This entity uses multiple `PhysicsImageShapeComponent` instances to create a tower-like structure. There are horizontal planks and vertical planks, arranged to form a grid-like shape.

### PhysicsJoint2Component

These components define the connections between different physics bodies (planks).

| Attribute              | Description                                                              |
| :--------------------- | :----------------------------------------------------------------------- |
| `type`                 | The type of joint. `WELD_JOINT` means the bodies are fixed together.     |
| `break_force`          | The force required to break this joint.                                  |
| `break_on_shear_angle_deg` | The angle in degrees at which the joint will break due to shear.         |
| `offset_x`             | Offset of the joint connection point on the X-axis.                      |
| `offset_y`             | Offset of the joint connection point on the Y-axis.                      |
| `body1_id`             | The `body_id` of the first physics body connected by the joint.          |
| `body2_id`             | The `body_id` of the second physics body connected by the joint.         |

**Summary of `PhysicsJoint2Component` instances:**
This entity uses numerous `WELD_JOINT` components to connect the various planks together, forming a rigid structure. Joints are placed to connect adjacent horizontal and vertical planks, creating a stable tower. The `break_force` and `break_on_shear_angle_deg` attributes are set to values that would require significant force to break these connections.

```xml
<Entity serialize="1">

  <PhysicsBody2Component 
      allow_sleep="1"
      angular_damping="0"
      linear_damping="0" 
      kill_entity_after_initialized="1"
      init_offset_x="32"
      init_offset_y="192"
  ></PhysicsBody2Component>

  <!-- Horizontal Planks -->
  <PhysicsImageShapeComponent
      body_id="0"
      offset_x="2"
      offset_y="0"
      image_file="data/props_breakable_gfx/plank_horizontal_64_00.png"
      material="wood_prop" 
  ></PhysicsImageShapeComponent>
  <PhysicsImageShapeComponent
      body_id="1"
      offset_x="2"
      offset_y="64"
      image_file="data/props_breakable_gfx/plank_horizontal_64_00.png"
      material="wood_prop" 
  ></PhysicsImageShapeComponent>
  <PhysicsImageShapeComponent
      body_id="2"
      offset_x="2"
      offset_y="128"
      image_file="data/props_breakable_gfx/plank_horizontal_64_00.png"
      material="wood_prop" 
  ></PhysicsImageShapeComponent>

  <!-- Vertical Planks (Left Column) -->
  <PhysicsImageShapeComponent
      body_id="10"
      offset_x="0"
      offset_y="0"
      image_file="data/props_breakable_gfx/plank_vertical_64_00.png"
      material="wood_prop" 
  ></PhysicsImageShapeComponent>
  <PhysicsImageShapeComponent
      body_id="11"
      offset_x="0"
      offset_y="64"
      image_file="data/props_breakable_gfx/plank_vertical_64_00.png"
      material="wood_prop" 
  ></PhysicsImageShapeComponent>
  <PhysicsImageShapeComponent
      body_id="12"
      offset_x="0"
      offset_y="128"
      image_file="data/props_breakable_gfx/plank_vertical_64_00.png"
      material="wood_prop" 
  ></PhysicsImageShapeComponent>

  <!-- Vertical Planks (Right Column) -->
  <PhysicsImageShapeComponent
      body_id="20"
      offset_x="66"
      offset_y="0"
      image_file="data/props_breakable_gfx/plank_vertical_64_00.png"
      material="wood_prop" 
  ></PhysicsImageShapeComponent>
  <PhysicsImageShapeComponent
      body_id="21"
      offset_x="66"
      offset_y="64"
      image_file="data/props_breakable_gfx/plank_vertical_64_00.png"
      material="wood_prop" 
  ></PhysicsImageShapeComponent>
  <PhysicsImageShapeComponent
      body_id="22"
      offset_x="66"
      offset_y="128"
      image_file="data/props_breakable_gfx/plank_vertical_64_00.png"
      material="wood_prop" 
  ></PhysicsImageShapeComponent>
  
  <!-- Vertical Joints -->
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="0.8"
      break_on_shear_angle_deg="2"
      offset_x="0"
      offset_y="64"
      body1_id="10"
      body2_id="11"
  ></PhysicsJoint2Component>
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="1.3"
      break_on_shear_angle_deg="2"
      offset_x="0"
      offset_y="128"
      body1_id="11"
      body2_id="12"
  ></PhysicsJoint2Component>
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="0.8"
      break_on_shear_angle_deg="2"
      offset_x="66"
      offset_y="64"
      body1_id="20"
      body2_id="21"
  ></PhysicsJoint2Component>
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="1.3"
      break_on_shear_angle_deg="2"
      offset_x="66"
      offset_y="128"
      body1_id="21"
      body2_id="22"
  ></PhysicsJoint2Component>

  <!-- Horizontal Joints -->
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="0.8"
      break_on_shear_angle_deg="2"
      offset_x="2"
      offset_y="0"
      body1_id="0"
      body2_id="10"
  ></PhysicsJoint2Component>
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="0.8"
      break_on_shear_angle_deg="2"
      offset_x="64"
      offset_y="0"
      body1_id="0"
      body2_id="20"
  ></PhysicsJoint2Component>
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="0.8"
      break_on_shear_angle_deg="2"
      offset_x="2"
      offset_y="64"
      body1_id="1"
      body2_id="11"
  ></PhysicsJoint2Component>
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="0.8"
      break_on_shear_angle_deg="2"
      offset_x="64"
      offset_y="64"
      body1_id="1"
      body2_id="21"
  ></PhysicsJoint2Component>
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="0.8"
      break_on_shear_angle_deg="2"
      offset_x="2"
      offset_y="128"
      body1_id="2"
      body2_id="12"
  ></PhysicsJoint2Component>
  <PhysicsJoint2Component
      type="WELD_JOINT"
      break_force="0.8"
      break_on_shear_angle_deg="2"
      offset_x="64"
      offset_y="128"
      body1_id="2"
      body2_id="22"
  ></PhysicsJoint2Component>

</Entity>
```