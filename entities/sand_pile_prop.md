---
title: Sand Pile Prop
category: entities
---

---

# Sand Pile Prop

This document describes the `sand_pile_01.xml` entity, a prop found in the overworld.

## Entity Definition

The `sand_pile_01.xml` file defines a simple prop entity with visual representation and a limited lifespan.

### Key Components

*   **PixelSceneComponent**: This component handles the visual aspect of the prop.
    *   `pixel_scene`: Specifies the image file used for the prop's appearance (`data/biome_impl/overworld/sand_pile_01.png`).
    *   `offset_x`: Horizontal offset for the visual element.
    *   `offset_y`: Vertical offset for the visual element.

*   **LifetimeComponent**: This component determines how long the entity persists in the game world.
    *   `lifetime`: The duration in seconds the prop will exist before disappearing (set to `2` seconds).