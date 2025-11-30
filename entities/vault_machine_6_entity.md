---
title: Vault Machine 6 Entity
category: entities
---

# Vault Machine 6 Entity

This document describes the `vault_machine_6.xml` entity, a prop used in Noita.

## Entity Definition

The core entity definition for the vault machine.

```xml
<Entity tags="pixelsprite">
  <!-- Components go here -->
</Entity>
```

## Key Components

### PixelSpriteComponent

This component defines the visual representation of the vault machine.

| Attribute     | Value                               | Description                                                                 |
|---------------|-------------------------------------|-----------------------------------------------------------------------------|
| `image_file`  | `data/props_gfx/vault_machine_6.png` | Path to the sprite image used for this entity.                              |
| `anchor_x`    | `10`                                | X-axis anchor point for the sprite.                                         |
| `anchor_y`    | `29`                                | Y-axis anchor point for the sprite.                                         |
| `material`    | `metal_nohit`                       | The material of the sprite, affecting its interaction with damage/physics. |

### SimplePhysicsComponent

This component governs basic physics properties.

| Attribute   | Value | Description                                                              |
|-------------|-------|--------------------------------------------------------------------------|
| `can_go_up` | `0`   | Prevents the entity from moving upwards.                                 |

### VelocityComponent

This component is present but has no specific attributes defined, indicating it uses default velocity behavior.