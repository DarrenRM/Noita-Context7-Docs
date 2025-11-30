---
title: Mountain Left Entrance Grass
category: entities
---

# Mountain Left Entrance Grass

This entity represents a grass sprite found at the left entrance of the mountain biome in Noita. It's a visual prop with basic physics properties.

## Key Components

### PixelSpriteComponent

This component defines the visual representation of the grass.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `image_file`      | Path to the sprite image: `data/biome_impl/mountain/left_entrance_grass.png` |
| `anchor_x`        | X-coordinate of the sprite's anchor point.                               |
| `anchor_y`        | Y-coordinate of the sprite's anchor point.                               |
| `create_box2d_bodies` | Enables the creation of Box2D physics bodies for collision.             |
| `clean_overlapping_pixels` | Removes overlapping pixels to ensure a clean sprite rendering.         |

### SimplePhysicsComponent

This component handles basic physics interactions.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `can_go_up` | Prevents the entity from moving upwards.        |

### VelocityComponent

This component is present but has no specific configurations, indicating it can inherit default velocity properties if needed.

## Tags

*   `vegetation`: Identifies this entity as a type of vegetation.
*   `pixelsprite`: Indicates that the entity uses a pixel sprite for its visual representation.