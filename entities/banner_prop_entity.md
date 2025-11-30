---
title: Banner Prop Entity
category: entities
---

# Banner Prop Entity

This document describes the `banner.xml` entity, which represents a decorative banner prop in Noita.

## Key Components

### SpriteComponent
This component defines the visual appearance of the banner.

*   **`image_file`**: Specifies the graphical asset used for the banner.
    *   Value: `"data/props_gfx/banner.xml"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"0"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"0"`
*   **`z_index`**: Determines the rendering order of the sprite.
    *   Value: `"1"`

### VelocityComponent
This component indicates that the entity has velocity properties, though it's typically static for a prop.

### SimplePhysicsComponent
This component suggests that the entity interacts with basic physics, likely for collision detection or placement.

## Usage

Banners are primarily decorative props placed within the game world. They do not typically have complex behaviors or interactions beyond their visual presence.