---
title: Boss Arena Statue 1
category: entities
---

# Boss Arena Statue 1

This entity represents a statue found in the boss arena. It's a static prop with basic physics.

## Components

### PixelSpriteComponent

This component defines the visual representation of the statue.

| Attribute         | Value                               | Description                                                                 |
|-------------------|-------------------------------------|-----------------------------------------------------------------------------|
| `image_file`      | `data/biome_impl/boss_arena_statue_1.png` | Path to the sprite image.                                                   |
| `anchor_x`        | `181`                               | X-coordinate of the sprite's anchor point.                                  |
| `anchor_y`        | `192`                               | Y-coordinate of the sprite's anchor point.                                  |
| `create_box2d_bodies` | `1`                                 | Enables the creation of Box2D physics bodies for collision detection.      |
| `clean_overlapping_pixels` | `1`                                 | Cleans up overlapping pixels in the sprite for better rendering.            |
| `material`        | `rock_loose`                        | The material type, influencing its physical properties and interactions.    |

### SimplePhysicsComponent

This component adds basic physics properties to the entity.

| Attribute     | Value | Description                               |
|---------------|-------|-------------------------------------------|
| `can_go_up`   | `0`   | Prevents the entity from moving upwards.  |

### VelocityComponent

This component is present but has no specific attributes defined, indicating it uses default velocity behavior.