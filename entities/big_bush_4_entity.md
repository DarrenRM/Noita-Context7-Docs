---
title: Big Bush 4 Entity
category: entities
---

# Big Bush 4 Entity

This document describes the `plant_bush_big_4.xml` entity, a large bush asset used in Noita.

## Entity Definition

The core entity definition for this bush.

```xml
<Entity
  name="unknown"
  tags="vegetation,pixelsprite" >
  <!-- ... components ... -->
</Entity>
```

*   **name**: "unknown" - This is a placeholder and could be more descriptive.
*   **tags**: `vegetation`, `pixelsprite` - Indicates its nature as a plant and its visual representation.

## PixelSpriteComponent

Defines the visual appearance of the bush.

```xml
<PixelSpriteComponent
  _enabled="1"
  image_file="data/vegetation/lush_bush_04.png"
  anchor_x="24"
  anchor_y="46"
  clean_overlapping_pixels="0" >
</PixelSpriteComponent>
```

*   **image\_file**: `data/vegetation/lush_bush_04.png` - The sprite asset used for this bush.
*   **anchor\_x**: `24` - The horizontal anchor point for the sprite.
*   **anchor\_y**: `46` - The vertical anchor point for the sprite.
*   **clean\_overlapping\_pixels**: `0` - Controls how overlapping pixels are handled.

## SimplePhysicsComponent

Basic physics properties for the entity.

```xml
<SimplePhysicsComponent
  can_go_up="0"
  >
</SimplePhysicsComponent>
```

*   **can\_go\_up**: `0` - Prevents the entity from moving upwards.

## VelocityComponent

A standard component for entities that can have velocity.

```xml
<VelocityComponent />
```

This component is present but has no specific attributes defined in this instance, implying default behavior.