---
title: Vault Machine 5 Prop
category: entities
---

# Vault Machine 5 Prop

This document describes the `vault_machine_5.xml` entity, which represents a prop in Noita.

## Entity Definition

The core entity definition for the vault machine.

```xml
<Entity tags="pixelsprite">
  <!-- Components are defined below -->
</Entity>
```

## Key Components

### PixelSpriteComponent

This component handles the visual representation of the vault machine.

```xml
<PixelSpriteComponent
    _enabled="1"
    image_file="data/props_gfx/vault_machine_5.png"
    anchor_x="10"
    anchor_y="29"
    clean_overlapping_pixels="0"
    material="metal_nohit"
>
</PixelSpriteComponent>
```

*   **`image_file`**: Specifies the texture file used for the sprite.
*   **`anchor_x`, `anchor_y`**: Define the sprite's anchor point for positioning.
*   **`material`**: Sets the material of the sprite, in this case, `metal_nohit` which implies it cannot be damaged by hits.

### SimplePhysicsComponent

This component defines basic physics properties.

```xml
<SimplePhysicsComponent
    can_go_up="0"
>
</SimplePhysicsComponent>
```

*   **`can_go_up`**: Set to `0`, indicating the prop cannot move upwards.

### VelocityComponent

This component is present but has no specific attributes defined, suggesting it uses default velocity behavior.

```xml
<VelocityComponent />
```