---
title: Vault Machine 1 Entity
category: entities
---

# Vault Machine 1 Entity

This document describes the `vault_machine_1.xml` entity, a prop found in Noita.

## Entity Definition

The core entity definition for the Vault Machine 1.

```xml
<Entity tags="pixelsprite">
  <!-- Components are defined below -->
</Entity>
```

## Key Components

### PixelSpriteComponent

This component defines the visual representation of the Vault Machine 1.

| Attribute     | Value                               | Description                                                                 |
|---------------|-------------------------------------|-----------------------------------------------------------------------------|
| `image_file`  | `data/props_gfx/vault_machine_1.png` | Path to the sprite image used for this entity.                              |
| `anchor_x`    | `10`                                | X-axis anchor point for the sprite.                                         |
| `anchor_y`    | `29`                                | Y-axis anchor point for the sprite.                                         |
| `material`    | `metal_nohit`                       | The material type, affecting its interaction with damage and physics.       |

### SimplePhysicsComponent

This component governs the basic physics properties of the entity.

| Attribute    | Value | Description                                                              |
|--------------|-------|--------------------------------------------------------------------------|
| `can_go_up`  | `0`   | Prevents the entity from moving upwards.                                 |

### VelocityComponent

This component is present and likely handles velocity-related properties, though no specific attributes are defined in this snippet.