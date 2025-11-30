---
title: Boss Victory Room Mechanism
category: entities
---

# Boss Victory Room Mechanism

This entity represents the mechanism found in the boss victory room, likely related to the centipede boss.

## Key Components

### SpriteComponent
This component defines the visual representation of the mechanism.

*   **image_file**: `data/entities/animals/boss_centipede/boss_victoryroom_mechanism_sprite.xml` - Specifies the sprite definition file.
*   **offset_x**: `0` - Horizontal offset of the sprite.
*   **offset_y**: `0` - Vertical offset of the sprite.
*   **z_index**: `1.5` - Determines the rendering order of the sprite.

## Tags

*   `teleportable_NOT`: Indicates that this entity cannot be teleported.
*   `ending_mechanism`: Suggests this entity plays a role in the game's ending sequence.