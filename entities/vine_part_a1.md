---
title: Vine Part A1
category: entities
---

# Vine Part A1

This entity defines a single segment of a vine, specifically the 'A1' variant. It's a visual component that forms part of a larger, dynamically breaking vine structure.

## SpriteComponent

This component handles the visual representation of the vine segment.

### Key Attributes:

*   **image\_file**: `data/entities/verlet_chains/vines/vine_parts/vine_a_1.xml` - Specifies the image file used for this vine segment.
*   **offset\_x**: `0` - Horizontal offset for the sprite.
*   **offset\_y**: `1.5` - Vertical offset for the sprite.
*   **update\_transform**: `0` - Indicates whether the sprite's transform (position, rotation, scale) should be updated dynamically. `0` means it's static relative to its entity.
*   **update\_transform\_rotation**: `0` - Indicates whether the sprite's rotation should be updated dynamically. `0` means it's static.