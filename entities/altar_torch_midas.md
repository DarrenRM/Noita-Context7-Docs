---
title: Altar Torch Midas
category: entities
---

# Altar Torch Midas

This entity represents a Midas-themed altar torch, primarily used for visual effects and ambient lighting. It inherits functionality from `base_torch_particle.xml`.

## Key Components

### Entity

*   **name**: `unknown` (This is a placeholder and might be intended to be more specific).
*   **tags**: `vegetation`, `altar_torch` - Indicates its nature as a decorative, possibly environmental, torch.

### PhysicsBodyComponent

This component defines the physical properties of the torch.

*   **is\_static**: `1` - The torch is fixed in place and does not move.
*   **allow\_sleep**: `1` - Allows the physics body to enter a sleep state when not in motion.
*   **fixed\_rotation**: `1` - Prevents the torch from rotating.
*   **auto\_clean**: `1` - The entity will be automatically cleaned up when no longer needed.

### PhysicsImageShapeComponent

Defines the visual representation and collision shape of the torch.

*   **image\_file**: `data/props_gfx/altar_torch_midas.png` - Specifies the sprite used for the torch.
*   **material**: `templebrick_static` - The material type, likely influencing its interaction with other game elements.

### VelocityComponent

*   This component is present but empty, indicating no initial velocity is applied.

### Base (Inherited from `base_torch_particle.xml`)

This section details the particle effects that make the torch appear lit.

#### ParticleEmitterComponent (x3)

These components are responsible for emitting particles to simulate fire and sparks.

*   **\_tags**: `fire` - Groups these emitters under a "fire" tag.
*   **\_enabled**: `1` - Ensures the particle emitters are active.
*   **offset.x**: `7.5`
*   **offset.y**: `5` - These offsets position the particle emission relative to the torch's origin.
*   **emitted\_material\_name**: Varies between `spark` and `spark_green`, creating a dynamic visual effect.
*   **x\_pos\_offset\_min / x\_pos\_offset\_max**: These attributes control the horizontal spread and variation of the emitted particles, creating a flickering flame effect.

**Summary of Particle Emitters:**

| Attribute               | Value (Emitter 1) | Value (Emitter 2) | Value (Emitter 3) |
| :---------------------- | :---------------- | :---------------- | :---------------- |
| \_tags                  | `fire`            | `fire`            | `fire`            |
| \_enabled               | `1`               | `1`               | `1`               |
| offset.x                | `7.5`             | `7.5`             | `7.5`             |
| offset.y                | `5`               | `5`               | `5`               |
| x\_pos\_offset\_min     | `-3`              | `-4`              | `-3`              |
| x\_pos\_offset\_max     | `3`               | `2`               | `3`               |
| emitted\_material\_name | `spark`           | `spark_green`     | `spark`           |