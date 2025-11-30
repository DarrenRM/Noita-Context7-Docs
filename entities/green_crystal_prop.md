---
title: Green Crystal Prop
category: entities
---

# Green Crystal Prop

This document describes the `crystal_green.xml` entity, a prop found in Noita. It's a breakable crystal that releases green sparks and a special effect upon destruction.

## Key Attributes

### `Entity`
- **tags**: `mortal` - Indicates the entity can be destroyed.

### `Base`
- **file**: `data/entities/base_prop_crystal.xml` - Inherits properties from a generic crystal base.

### `PhysicsImageShapeComponent`
- **image_file**: `data/props_gfx/crystal_green.png` - The visual sprite for the crystal.
- **material**: `crystal_solid` - The physical material properties of the crystal.

### `MaterialInventoryComponent`
- **count_per_material_type**:
    - **Material**: `spark_green`
    - **count**: `300` - When broken, the crystal drops 300 units of `spark_green` material.

### `DamageModelComponent`
- **blood_material**: `spark_green` - The material that is "bled" or released when the crystal takes damage.

### `ExplodeOnDamageComponent`
- **config_explosion**:
    - **load_this_entity**: `data/entities/particles/particle_explosion/main_swirly_green.xml,data/entities/props/crystal_green_effect.xml` - Specifies the entities to spawn upon destruction, including a particle effect and a custom effect.

### `ParticleEmitterComponent`
- **emitted_material_name**: `spark_green` - The material emitted by the particle emitter, likely for ambient effects.

### `LightComponent`
- **r**: `20`
- **g**: `255`
- **b**: `20` - Defines the green color of the light emitted by the crystal.