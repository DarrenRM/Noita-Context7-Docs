---
title: Boss Arena Statue 3 Prop
category: entities
---

# Boss Arena Statue 3 Prop

This entity defines a prop used in the boss arena, specifically a statue.

## Key Components

### PixelSpriteComponent
This component handles the visual representation of the statue.

| Attribute        | Value                               | Description                                                                 |
|------------------|-------------------------------------|-----------------------------------------------------------------------------|
| `image_file`     | `data/biome_impl/boss_arena_statue_3.png` | Path to the sprite image for the statue.                                    |
| `anchor_x`       | `181`                               | X-coordinate of the sprite's anchor point.                                  |
| `anchor_y`       | `192`                               | Y-coordinate of the sprite's anchor point.                                  |
| `create_box2d_bodies` | `1`                                 | Enables the creation of Box2D physics bodies for collision detection.      |
| `clean_overlapping_pixels` | `1`                                 | Removes overlapping pixels to ensure a clean sprite rendering.              |
| `material`       | `rock_loose`                        | The material type of the sprite, influencing its physical properties.       |

### SimplePhysicsComponent
This component defines basic physics properties for the entity.

| Attribute    | Value | Description                                     |
|--------------|-------|-------------------------------------------------|
| `can_go_up`  | `0`   | Prevents the entity from moving upwards.        |

### VelocityComponent
This component is present but has no specific attributes defined, indicating it uses default velocity behavior.