---
title: Quantum Split FX Blue
category: entities
---

# Quantum Split FX Blue

This entity defines a visual effect for the "quantum split" mechanic, specifically the blue variant. It inherits its base properties from `quantum_split_fx_red.xml` and customizes its visual appearance and particle emission.

## Key Components

### Base Entity

*   **Inheritance:** `data/entities/misc/quantum_split_fx_red.xml` - This indicates that the entity reuses most of its properties from the red quantum split effect, only overriding specific elements.

### Sprite Component

*   **`image_file`**: `data/projectiles_gfx/quantum_fx_blue.xml`
    *   This attribute specifies the graphical asset used for the visual effect. It points to a separate XML file that likely defines the sprite's animation, frames, and other visual properties.

### Particle Emitter Component

*   **`emitted_material_name`**: `plasma_fading`
    *   This defines the material of the particles that are emitted by this effect. `plasma_fading` suggests particles that resemble fading plasma, contributing to the visual spectacle of the quantum split.