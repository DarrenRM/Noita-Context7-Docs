---
title: Lukki Dark Limb Animated
category: entities
---

# Lukki Dark Limb Animated

This entity defines an animated limb for the dark lukki creature in Noita. It utilizes multiple sprite components to create the visual appearance of a segmented limb.

## Key Components

### SpriteComponent

This component is responsible for rendering the visual assets of the limb. Multiple instances are used to represent different parts of the limb.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `image_file`     | Path to the sprite image. Different files are used for different limb segments (A, B, knee). |
| `z_index`        | Controls the rendering order of the sprite. `1.1` suggests it's rendered above other base elements. |
| `offset_x`       | Horizontal offset for the sprite's position.                             |
| `offset_y`       | Vertical offset for the sprite's position.                               |
| `update_transform` | If `0`, the sprite's transform (position, rotation, scale) is not updated by the game engine. |
| `update_transform_rotation` | If `0`, the sprite's rotation is not updated by the game engine. |

### IKLimbComponent

This component likely handles the Inverse Kinematics (IK) for the limb, allowing it to animate and connect to other parts of the creature.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `length`  | The defined length of the limb segment. |

### InheritTransformComponent

This component, when present, indicates that the entity inherits transform properties from its parent or a related entity. In this case, it's empty, suggesting it might not be actively used or is a placeholder.