---
title: Altar Torch Entity
category: entities
---

# Altar Torch Entity

This document describes the `altar_torch.xml` entity, which represents a decorative torch found in Noita.

## Entity Definition

The `altar_torch` entity is a static prop with visual and particle effects.

```xml
<Entity 
  name="unknown" 
  tags="vegetation,altar_torch" >
  
  <!-- ... components ... -->
</Entity>
```

### Key Attributes:

*   **`name`**: "unknown" (This is a placeholder and might be intended to be more specific).
*   **`tags`**: `vegetation`, `altar_torch` (Used for identification and potential interactions).

## Components

### PhysicsBodyComponent

This component defines the physical properties of the altar torch.

```xml
<PhysicsBodyComponent 
  allow_sleep="1"
  angular_damping="0"
  is_bullet="0"
  linear_damping="0"
  is_static="1"
  fixed_rotation="1"
  auto_clean="1"
  >
</PhysicsBodyComponent>
```

*   **`is_static`**: `1` (Indicates the torch does not move).
*   **`fixed_rotation`**: `1` (Ensures the torch maintains its orientation).
*   **`auto_clean`**: `1` (Allows the entity to be cleaned up when no longer needed).

### PhysicsImageShapeComponent

This component defines the visual representation of the altar torch.

```xml
<PhysicsImageShapeComponent 
  image_file="data/props_gfx/altar_torch.png"
  material="templebrick_static" >
</PhysicsImageShapeComponent>
```

*   **`image_file`**: `data/props_gfx/altar_torch.png` (Specifies the sprite for the torch).
*   **`material`**: `templebrick_static` (Defines the material properties for physics interactions).

### VelocityComponent

This component is present but has no specific attributes defined, suggesting it's a standard inclusion for entities that might have velocity, even if static.

```xml
<VelocityComponent />
```

### Base (Particle Effects)

This section inherits from `base_torch_particle.xml` and defines particle emitters for fire effects.

```xml
<Base file="data/entities/base_torch_particle.xml" >
  <!-- ... ParticleEmitterComponents ... -->
</Base>
```

#### ParticleEmitterComponent (x3)

These components are responsible for generating the visual fire and spark effects.

```xml
<ParticleEmitterComponent
  _tags="fire"
  _enabled="0"
  offset.y="2"
  offset.x="7.5"
  x_pos_offset_min="-3"
  x_pos_offset_max="2" 
  emitted_material_name="spark_green"
  >
</ParticleEmitterComponent>
```

*   **`_tags`**: `fire` (Identifies these as fire-related emitters).
*   **`_enabled`**: `0` (This suggests the fire effect is disabled by default and likely needs to be triggered by game logic or other entities).
*   **`offset.x`, `offset.y`**: Position the emitters relative to the torch.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: Define the horizontal spread of the emitted particles.
*   **`emitted_material_name`**: `spark_green` (Specifies the material of the particles being emitted).
*   **`color`**: (Present in one emitter) `ff20f050` (Defines the color of the emitted sparks, in RGBA format).

**Note:** The `_enabled="0"` attribute on all `ParticleEmitterComponent`s indicates that the fire effect is not active by default. This implies that the torch's flame is likely controlled by external game events or scripts.