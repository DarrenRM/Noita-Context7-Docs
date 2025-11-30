---
title: Boss Arena Statue 4 Entity
category: entities
---

# Boss Arena Statue 4 Entity

This entity defines a decorative statue found in boss arenas. It's a static prop with basic physics properties.

## Key Components

### PixelSpriteComponent

This component handles the visual representation of the statue.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `image_file`     | Path to the sprite image (`data/biome_impl/boss_arena_statue_4.png`).   |
| `anchor_x`       | X-coordinate of the sprite's anchor point.                               |
| `anchor_y`       | Y-coordinate of the sprite's anchor point.                               |
| `create_box2d_bodies` | Enables the creation of Box2D physics bodies for collision.           |
| `clean_overlapping_pixels` | Removes overlapping pixels for cleaner rendering.                    |
| `material`       | The material of the sprite, affecting physics interactions (`rock_loose`). |

### SimplePhysicsComponent

This component defines basic physics behavior.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `can_go_up` | Prevents the entity from moving upwards. |

### VelocityComponent

This component is present but has no specific attributes defined, indicating it's a placeholder or uses default velocity behavior.