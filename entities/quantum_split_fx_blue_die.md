---
title: Quantum Split FX Blue Die
category: entities
---

# Quantum Split FX Blue Die

This entity defines the visual effects for when a "quantum split" effect dies, specifically the blue variant. It inherits its base functionality from `quantum_split_fx_red_die.xml` and customizes the particle effects.

## Key Components

### Base Entity

*   **`Base file="data/entities/misc/quantum_split_fx_red_die.xml"`**: This indicates that the entity inherits all properties and components from the red variant of the quantum split death effect. Modifications are applied on top of this base.

### Particle Emitter Component

*   **`emitted_material_name="plasma_fading"`**: This is the primary customization. It specifies that the particles emitted during this death effect will be of the `plasma_fading` material. This likely results in a blue, fading plasma-like visual.