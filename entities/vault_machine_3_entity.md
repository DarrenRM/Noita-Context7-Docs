---
title: Vault Machine 3 Entity
category: entities
---

# Vault Machine 3 Entity

This document describes the `vault_machine_3.xml` entity, a prop used in Noita.

## Entity Definition

The core entity definition for the vault machine.

```xml
<Entity tags="pixelsprite">
  <!-- Components -->
</Entity>
```

### Key Attributes:

*   **tags**: `pixelsprite` - Indicates this entity is a sprite-based object.

## Components

### PixelSpriteComponent

Defines the visual representation of the vault machine.

```xml
<PixelSpriteComponent 
  _enabled="1" 
  image_file="data/props_gfx/vault_machine_3.png" 
  anchor_x="10" 
  anchor_y="29"
  clean_overlapping_pixels="0"
  material="metal_nohit"
>
</PixelSpriteComponent>
```

#### Key Attributes:

*   **image\_file**: `data/props_gfx/vault_machine_3.png` - The sprite image used for this entity.
*   **anchor\_x**: `10` - The X-axis anchor point for the sprite.
*   **anchor\_y**: `29` - The Y-axis anchor point for the sprite.
*   **material**: `metal_nohit` - Specifies the material properties, indicating it's a non-damagable metal.

### SimplePhysicsComponent

Handles basic physics properties for the entity.

```xml
<SimplePhysicsComponent 
  can_go_up="0"
>
</SimplePhysicsComponent >
```

#### Key Attributes:

*   **can\_go\_up**: `0` - Prevents the entity from moving upwards.

### VelocityComponent

A standard component for entities that can have velocity.

```xml
<VelocityComponent />
```

#### Key Attributes:

*   This component is present but has no specific configuration in this entity, implying default velocity behavior.