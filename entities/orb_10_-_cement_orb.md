---
title: Orb 10 - Cement Orb
category: entities
---

# Orb 10 - Cement Orb

This document details the configuration for Orb 10, commonly known as the Cement Orb, within the Noita game data.

## Core Entity Configuration

The primary entity defines the orb's fundamental properties and its visual representation.

### Key Attributes:

*   **`tags`**: `hittable,teleportable_NOT` - Indicates the orb can be hit by projectiles and cannot be teleported.
*   **`Base file="data/entities/items/orbs/orb_base.xml"`**: Inherits core functionality from a generic orb base.

### Orb Component:

*   **`orb_id="10"`**: Assigns this orb a unique identifier within the game's orb system.

### Sprite Component:

*   **`image_file="data/items_gfx/orbs/orb_10.xml"`**: Specifies the graphical asset used for rendering the orb.

### Variable Storage Component:

*   **`name="card_name"`**: Stores a string identifier.
*   **`value_string="MATERIAL_CEMENT"`**: Associates this orb with the "Cement" material type.

## Visual and Particle Effects

A nested entity handles specific visual positioning and particle effects associated with the orb.

### Inherited Transform Component:

*   **`position.x="0"`**: Sets the horizontal offset relative to the orb's base position.
*   **`position.y="-11"`**: Sets the vertical offset relative to the orb's base position.

### Base Particle Effects:

*   **`Base file="data/entities/items/orbs/orb_particles_base.xml"`**: Inherits standard particle effects defined for orbs.