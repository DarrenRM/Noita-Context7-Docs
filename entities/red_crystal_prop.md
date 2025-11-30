---
title: Red Crystal Prop
category: entities
---

# Red Crystal Prop

This document describes the `crystal_red.xml` entity, a prop found in Noita. It's a breakable crystal that releases red sparks and explodes when damaged.

## Key Attributes

*   **`tags`**: `mortal` - Indicates the entity can be destroyed.
*   **`Base file`**: `data/entities/base_prop_crystal.xml` - Inherits core properties from a base crystal entity.

### `PhysicsImageShapeComponent`

Defines the physical properties and visual representation of the crystal.

*   **`image_file`**: `data/props_gfx/crystal_red.png` - The texture used for the crystal.
*   **`material`**: `crystal_solid` - The physical material type.

### `MaterialInventoryComponent`

Specifies the materials contained within the crystal.

*   **`count_per_material_type`**:
    *   **`Material material="spark_red" count="300"`**: Contains 300 units of `spark_red` material.

### `DamageModelComponent`

Determines how the entity reacts to damage.

*   **`blood_material`**: `spark_red` - The material that is released upon taking damage.

### `ExplodeOnDamageComponent`

Configures the explosion effect when the crystal is destroyed.

*   **`config_explosion`**:
    *   **`load_this_entity`**:
        *   `data/entities/particles/particle_explosion/main_swirly_red.xml`
        *   `data/entities/props/crystal_red_effect.xml` - Entities loaded upon explosion.

### `ParticleEmitterComponent`

Manages the emission of particles.

*   **`emitted_material_name`**: `spark_red` - The name of the material emitted as particles.