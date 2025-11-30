---
title: Vault Machine 2 Prop
category: entities
---

# Vault Machine 2 Prop

This document describes the `vault_machine_2.xml` entity, which represents a prop in Noita.

## Entity Definition

The core entity definition for the vault machine.

```xml
<Entity tags="pixelsprite">
  <!-- Components are defined below -->
</Entity>
```

## Key Components

### PixelSpriteComponent

This component defines the visual representation of the vault machine.

| Attribute     | Value                               | Description                                                                 |
|---------------|-------------------------------------|-----------------------------------------------------------------------------|
| `image_file`  | `data/props_gfx/vault_machine_2.png` | Path to the sprite image used for this prop.                                |
| `anchor_x`    | `10`                                | X-axis anchor point for the sprite.                                         |
| `anchor_y`    | `29`                                | Y-axis anchor point for the sprite.                                         |
| `material`    | `metal_nohit`                       | The material of the prop, affecting its interaction with damage and physics. |

### SimplePhysicsComponent

This component governs the basic physics properties of the prop.

| Attribute   | Value | Description                                                              |
|-------------|-------|--------------------------------------------------------------------------|
| `can_go_up` | `0`   | Prevents the prop from moving upwards.                                   |

### VelocityComponent

This component is present but has no specific attributes defined, indicating it uses default velocity behavior.