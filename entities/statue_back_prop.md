---
title: Statue Back Prop
category: entities
---

# Statue Back Prop

This entity defines a static prop with a pixel sprite, representing the back of a statue. It is designed to be placed in the game world and interacts with physics.

## Key Components and Attributes

### PixelSpriteComponent

This component handles the visual representation and basic physics setup for the prop.

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `_enabled`       | Whether the component is active (1 for enabled).                            |
| `image_file`     | Path to the sprite image (`data/props_gfx/statue_back.png`).                |
| `anchor_x`       | X-coordinate of the sprite's anchor point (8).                              |
| `anchor_y`       | Y-coordinate of the sprite's anchor point (39).                             |
| `create_box2d_bodies` | Whether to create Box2D physics bodies for collision (1 for enabled).      |
| `clean_overlapping_pixels` | Whether to clean overlapping pixels for better rendering (1 for enabled). |
| `material`       | The material of the prop, affecting its physical properties (`rock_loose`). |

### SimplePhysicsComponent

This component provides basic physics properties.

| Attribute    | Description                                       |
| :----------- | :------------------------------------------------ |
| `can_go_up`  | Whether the entity can move upwards (0 for false). |

### VelocityComponent

This component is present but has no specific attributes defined, indicating it uses default velocity behavior.