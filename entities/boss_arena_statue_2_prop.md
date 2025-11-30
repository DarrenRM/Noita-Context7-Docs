---
title: Boss Arena Statue 2 Prop
category: entities
---

# Boss Arena Statue 2 Prop

This entity defines a decorative statue found in boss arenas. It's a static prop with basic physics properties.

## Key Components

### PixelSpriteComponent
This component handles the visual representation of the statue.

*   **`image_file`**: `data/biome_impl/boss_arena_statue_2.png` - Specifies the sprite image used for the statue.
*   **`anchor_x`**: `181` - The horizontal anchor point for the sprite.
*   **`anchor_y`**: `192` - The vertical anchor point for the sprite.
*   **`create_box2d_bodies`**: `1` - Enables the creation of Box2D physics bodies for collision.
*   **`clean_overlapping_pixels`**: `1` - Helps in cleaning up overlapping pixels for a cleaner sprite rendering.
*   **`material`**: `rock_loose` - The material assigned to the sprite, influencing its physical properties.

### SimplePhysicsComponent
This component defines basic physics behavior.

*   **`can_go_up`**: `0` - Prevents the statue from moving upwards.

### VelocityComponent
This component is present but has no specific attributes defined, indicating it's a standard velocity component without custom settings.