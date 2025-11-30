---
title: Lukki Limb Attacker Entity
category: entities
---

# Lukki Limb Attacker Entity

This entity defines a component of a Lukki's limb that is capable of attacking. It primarily consists of sprite components for visual representation and an `IKLimbAttackerComponent` to define its attacking behavior.

## Key Components

### IKLimbAttackerComponent

This component dictates the attacking capabilities of the limb.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `radius`  | The radius within which the limb can attack. |

### IKLimbComponent

This component defines the physical properties of the limb segment.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `length`  | The length of this limb segment.          |

### SpriteComponent

Multiple `SpriteComponent`s are used to render different parts of the Lukki's limb.

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `image_file`   | Path to the image file for this sprite part (e.g., limb segment, knee). |
| `z_index`      | Controls the drawing order of sprites. Higher values are drawn on top.   |
| `offset_x`     | Horizontal offset for the sprite.                                        |
| `offset_y`     | Vertical offset for the sprite.                                          |
| `update_transform` | Whether the sprite's transform should be updated.                        |
| `update_transform_rotation` | Whether the sprite's rotation should be updated.                 |

## Example Usage

This entity is likely used as a child entity attached to a larger Lukki entity, contributing to its overall structure and attack mechanics.