---
title: Lukki Chest Limb Entity
category: entities
---

# Lukki Chest Limb Entity

This entity defines a component of the Lukki creature's body, specifically its chest limb. It utilizes several components to define its visual representation and its role as a walking limb.

## Key Components

### IKLimbWalkerComponent

This component signifies that the entity is a part of an Inverse Kinematics (IK) limb system designed for walking.

### IKLimbComponent

This component defines the basic properties of an IK limb.

*   **length**: The length of the limb segment.
    *   `40`

### SpriteComponent

This component defines the visual appearance of the limb. Multiple `SpriteComponent` instances are used to layer different parts of the limb.

*   **image\_file**: Path to the sprite image.
*   **z\_index**: Determines the rendering order of sprites. Higher values are drawn on top.
*   **offset\_x**: Horizontal offset for the sprite.
*   **offset\_y**: Vertical offset for the sprite.
*   **update\_transform**: Whether the sprite's transform should be updated.
*   **update\_transform\_rotation**: Whether the sprite's rotation should be updated.

#### Sprite Definitions:

| Attribute          | Value                                                | Description                               |
| :----------------- | :--------------------------------------------------- | :---------------------------------------- |
| `image_file`       | `data/entities/animals/lukki/lukki_feet/chest_limb_a.png` | Primary limb segment sprite.              |
| `z_index`          | `1.1`                                                | Renders above base body parts.            |
| `offset_x`         | `0`                                                  | No horizontal offset.                     |
| `offset_y`         | `5`                                                  | Slight vertical offset.                   |
| `update_transform` | `0`                                                  | Transform is static.                      |
| `update_transform_rotation` | `0`                                              | Rotation is static.                       |
| `image_file`       | `data/entities/animals/lukki/lukki_feet/chest_limb_b_left.png` | Secondary limb segment sprite.            |
| `z_index`          | `1.1`                                                | Renders above base body parts.            |
| `offset_x`         | `0`                                                  | No horizontal offset.                     |
| `offset_y`         | `5`                                                  | Slight vertical offset.                   |
| `update_transform` | `0`                                                  | Transform is static.                      |
| `update_transform_rotation` | `0`                                              | Rotation is static.                       |
| `image_file`       | `data/entities/animals/lukki/lukki_feet/chest_knee.png` | Knee joint sprite.                        |
| `z_index`          | `1.1`                                                | Renders above base body parts.            |
| `offset_x`         | `4`                                                  | Small horizontal offset.                  |
| `offset_y`         | `4`                                                  | Small vertical offset.                    |
| `update_transform` | `0`                                                  | Transform is static.                      |
| `update_transform_rotation` | `0`                                              | Rotation is static.                       |