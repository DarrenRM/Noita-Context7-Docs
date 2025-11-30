---
title: Vault Machine 4 Prop
category: entities
---

# Vault Machine 4 Prop

This document describes the `vault_machine_4.xml` entity, a prop used in Noita.

## Entity Definition

The core entity definition for the Vault Machine 4.

```xml
<Entity tags="pixelsprite">
  <!-- Components go here -->
</Entity>
```

### Key Attributes:

*   **tags**: `pixelsprite` - Indicates this entity is a sprite-based object.

## Components

### PixelSpriteComponent

Defines the visual representation of the Vault Machine 4.

```xml
<PixelSpriteComponent 
  _enabled="1" 
  image_file="data/props_gfx/vault_machine_4.png" 
  anchor_x="10" 
  anchor_y="29"
  clean_overlapping_pixels="0"
  material="metal_nohit"
>
</PixelSpriteComponent>
```

#### Key Attributes:

*   **image\_file**: `data/props_gfx/vault_machine_4.png` - The sprite image used for this prop.
*   **anchor\_x**: `10` - The horizontal anchor point for the sprite.
*   **anchor\_y**: `29` - The vertical anchor point for the sprite.
*   **material**: `metal_nohit` - The material type, affecting its interaction with damage and physics.

### SimplePhysicsComponent

Handles basic physics properties for the prop.

```xml
<SimplePhysicsComponent 
  can_go_up="0"
>
</SimplePhysicsComponent>
```

#### Key Attributes:

*   **can\_go\_up**: `0` - Prevents the prop from moving upwards.

### VelocityComponent

A standard component for entities that can have velocity.

```xml
<VelocityComponent />
```

This component is present but has no specific configuration in this entity, meaning it uses default velocity properties.