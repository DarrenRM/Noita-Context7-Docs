---
title: Orb 05 - Holy Bomb
category: entities
---

# Orb 05 - Holy Bomb

This entity defines the "Holy Bomb" orb in Noita. It inherits its base functionality from `orb_base.xml` and adds specific visual and gameplay elements.

## Key Components

### Base Entity

*   **`Base file="data/entities/items/orbs/orb_base.xml"`**: Inherits core orb properties and behaviors.

### Orb Component

*   **`OrbComponent orb_id="5"`**: Identifies this as the 5th orb in the game's internal system.

### Sprite Component

*   **`SpriteComponent image_file="data/items_gfx/orbs/orb_05.xml"`**: Specifies the graphical asset used for this orb.

### Variable Storage Component

*   **`VariableStorageComponent name="card_name" value_string="BOMB_HOLY"`**: Assigns the internal identifier "BOMB_HOLY" to this orb, likely used for referencing its associated spell or effect.

### Inherited Transform Component

*   **`InheritTransformComponent`**: Used to position child entities relative to the orb.
    *   **`Transform position.x="0" position.y="-11"`**: Offsets the child entity by 0 units horizontally and -11 units vertically.

### Particle Base

*   **`Base file="data/entities/items/orbs/orb_particles_base.xml"`**: Inherits particle effects associated with orbs, likely for visual flair.