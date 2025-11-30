---
title: Orb 06 - Spiral Shot
category: entities
---

# Orb 06 - Spiral Shot

This document details the configuration for Orb 06, specifically the "Spiral Shot" orb, within Noita's entity data.

## Core Entity Configuration

The primary entity defines the orb's fundamental properties and its visual representation.

### Key Attributes:

*   **`tags`**: `hittable`, `teleportable_NOT` - Indicates the orb can be hit and is not subject to teleportation.
*   **`Base file="data/entities/items/orbs/orb_base.xml"`**: Inherits core orb functionalities from a base configuration.

### Orb Component:

*   **`OrbComponent`**:
    *   `orb_id="6"`: Assigns a unique identifier to this specific orb type.

### Sprite Component:

*   **`SpriteComponent`**:
    *   `image_file="data/items_gfx/orbs/orb_06.xml"`: Specifies the graphical asset used for the orb's appearance.

### Variable Storage Component:

*   **`VariableStorageComponent`**:
    *   `name="card_name"`: Stores the internal name for the orb's associated spell.
    *   `value_string="SPIRAL_SHOT"`: The specific spell associated with this orb.

## Visual Effects and Positioning

This section defines the visual effects and relative positioning of the orb's particle system.

### Inherited Entity:

*   **`Entity`**: This nested entity handles the visual effects.
    *   **`InheritTransformComponent`**:
        *   **`Transform`**:
            *   `position.x="0"`: Sets the horizontal offset for the particle effect.
            *   `position.y="-11"`: Sets the vertical offset for the particle effect.
    *   **`Base file="data/entities/items/orbs/orb_particles_base.xml"`**: Inherits standard particle effects for orbs.