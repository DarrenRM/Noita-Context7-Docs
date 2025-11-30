---
title: Altar Torch (Old)
category: entities
---

# Altar Torch (Old)

This entity represents an old, static altar torch. It primarily serves as a visual prop with a particle effect for fire.

## Key Components

### Entity
- **name**: `unknown` (This is likely a placeholder and could be renamed for clarity.)
- **tags**: `vegetation`, `altar_torch` (Indicates its nature and potential interactions.)

### PhysicsBodyComponent
This component defines the physical properties of the torch.
- **is_static**: `1` (The torch does not move.)
- **fixed_rotation**: `1` (The torch's rotation is locked.)
- **auto_clean**: `1` (The entity will be automatically cleaned up when no longer needed.)

### PhysicsImageShapeComponent
Defines the visual representation and collision shape.
- **image_file**: `data/props_gfx/altar_torch.png` (The sprite used for the torch.)
- **material**: `templebrick_static` (The material properties for collision.)

### Base
Inherits properties from `data/entities/base_torch_particle.xml`. This is where the particle effects are defined.

### ParticleEmitterComponent (Multiple Instances)
These components are responsible for generating fire and spark effects.
- **_tags**: `fire` (Identifies the particle effect type.)
- **_enabled**: `0` (By default, the fire effect is disabled. This suggests it might be triggered by game events or scripts.)
- **offset.y**: `2`
- **offset.x**: `7.5` (These offsets position the particle emitter relative to the torch's origin.)
- **x_pos_offset_min/max**: Controls the horizontal spread of the emitted particles.
- **emitted_material_name**: `spark_green` (The material of the particles being emitted.)
- **color**: `ff20f050` (One of the emitters has a specific green color applied.)

## Summary

The `altar_torch_old.xml` defines a static prop with a visual sprite and a disabled particle emitter for fire effects. Its primary function is decorative, with the potential for dynamic activation of its fire particle system through external scripting. The `_enabled="0"` attribute is a key point for modders looking to control when the torch ignites.