---
title: Dripping Oil Prop
category: entities
---

# Dripping Oil Prop

This entity defines a prop that drips oil. It inherits its core functionality from `base_dripping_liquid.xml`.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_dripping_liquid.xml"`**: This indicates that the `dripping_oil.xml` entity inherits all properties and behaviors from the `base_dripping_liquid.xml` file. This is the primary source of its dripping mechanics.

### Particle Emitters

The entity uses two `ParticleEmitterComponent` instances to generate oil particles.

*   **`ParticleEmitterComponent`**:
    *   **`emitted_material_name="oil"`**: This crucial attribute specifies that the particles being emitted are of the "oil" material. This determines the visual appearance and physical properties of the dripping substance.

## Attributes

| Attribute             | Value                               | Description                                                                 |
| :-------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `tags`                | `mortal, hittable`                  | Indicates the entity can be destroyed and can be interacted with by damage. |
| `emitted_material_name` | `oil`                               | Specifies the material of the emitted particles.                            |